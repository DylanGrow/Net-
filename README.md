Net + Study

Google Meet joining info
Video call link: https://meet.google.com/hqw-rppc-tkb

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>OSI Model — Interactive</title>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
      background: #0f0f13;
      color: #e8e8e8;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 32px 16px;
    }

    .container {
      width: 100%;
      max-width: 680px;
    }

    h1 {
      font-size: 13px;
      font-weight: 600;
      letter-spacing: .08em;
      text-transform: uppercase;
      color: #888;
      margin-bottom: 20px;
      text-align: center;
    }

    @keyframes slideIn {
      from { opacity:0; transform: translateX(-60px); }
      to   { opacity:1; transform: translateX(0); }
    }
    @keyframes pulse {
      0%,100% { box-shadow: 0 0 0 0 var(--glow); }
      50%      { box-shadow: 0 0 0 6px transparent; }
    }
    @keyframes fadeUp {
      from { opacity:0; transform:translateY(10px); }
      to   { opacity:1; transform:translateY(0); }
    }
    @keyframes typewriter {
      from { width:0; }
      to   { width:100%; }
    }

    .layer {
      position: relative;
      border-radius: 10px;
      margin-bottom: 5px;
      cursor: pointer;
      transition: transform .2s, filter .2s;
      animation: slideIn .4s ease both;
      display: flex;
      align-items: center;
      padding: 0 14px;
      height: 60px;
      border: 1.5px solid transparent;
      user-select: none;
    }
    .layer:hover  { transform: translateX(6px) scale(1.01); filter: brightness(1.08); }
    .layer.active { transform: translateX(8px) scale(1.02); filter: brightness(1.13); border-color: rgba(255,255,255,0.4) !important; animation: pulse 2s infinite; }

    .layer-num   { font-size: 22px; font-weight: 700; opacity: .9; min-width: 34px; }
    .layer-name  { font-size: 15px; font-weight: 600; flex: 1; padding-left: 10px; }
    .layer-proto { font-size: 11px; font-weight: 500; opacity: .75; white-space: nowrap; overflow: hidden; }

    .tw.run { animation: typewriter .7s steps(30) both; }

    .detail-panel {
      border-radius: 12px;
      padding: 18px 20px;
      margin-bottom: 8px;
      animation: fadeUp .3s ease both;
      border: 1.5px solid rgba(255,255,255,0.18);
      display: none;
    }
    .detail-panel.visible { display: block; }
    .detail-title { font-size: 16px; font-weight: 700; margin-bottom: 6px; }
    .detail-desc  { font-size: 13px; line-height: 1.6; margin-bottom: 10px; opacity: .9; }

    .tag {
      display: inline-block;
      border-radius: 20px;
      padding: 3px 10px;
      font-size: 11px;
      font-weight: 600;
      margin: 2px;
    }

    .example-row { font-size: 12px; margin-top: 8px; opacity: .8; }
    .example-row span { font-weight: 600; }

    .packet {
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
      width: 14px;
      height: 14px;
      border-radius: 50%;
      z-index: 20;
      pointer-events: none;
    }

    .legend {
      margin-top: 14px;
      font-size: 12px;
      color: #888;
      display: flex;
      gap: 16px;
      align-items: center;
    }
    .legend-dot {
      width: 12px; height: 12px;
      border-radius: 50%;
      background: #f9a825;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>OSI Model — 7 Layers</h1>

    <div style="display:flex; gap:10px; align-items:flex-start;">

      <!-- Packet column -->
      <div style="width:26px; flex-shrink:0; position:relative; align-self:stretch;">
        <div class="packet" id="pkt" style="background:#f9a825; opacity:0; top:490px;"></div>
      </div>

      <!-- Layers column -->
      <div style="flex:1;">
        <div class="layer" id="l7" style="background:#7b2ff7; --glow:#7b2ff755; animation-delay:.05s;" onclick="toggle(7)">
          <div class="layer-num">7</div>
          <div class="layer-name">Application</div>
          <div class="layer-proto tw" id="p7">HTTP · DNS · FTP · SMTP · SSH</div>
        </div>
        <div class="layer" id="l6" style="background:#d63af9; --glow:#d63af955; animation-delay:.1s;" onclick="toggle(6)">
          <div class="layer-num">6</div>
          <div class="layer-name">Presentation</div>
          <div class="layer-proto tw" id="p6">TLS · SSL · JPEG · MPEG · ASCII</div>
        </div>
        <div class="layer" id="l5" style="background:#f74e8e; --glow:#f74e8e55; animation-delay:.15s;" onclick="toggle(5)">
          <div class="layer-num">5</div>
          <div class="layer-name">Session</div>
          <div class="layer-proto tw" id="p5">NetBIOS · PPTP · RPC · SIP</div>
        </div>
        <div class="layer" id="l4" style="background:#f9771e; --glow:#f9771e55; animation-delay:.2s;" onclick="toggle(4)">
          <div class="layer-num">4</div>
          <div class="layer-name">Transport</div>
          <div class="layer-proto tw" id="p4">TCP · UDP · SCTP · QUIC</div>
        </div>
        <div class="layer" id="l3" style="background:#e8b800; --glow:#e8b80055; animation-delay:.25s;" onclick="toggle(3)">
          <div class="layer-num">3</div>
          <div class="layer-name">Network</div>
          <div class="layer-proto tw" id="p3">IP · ICMP · OSPF · BGP · ARP</div>
        </div>
        <div class="layer" id="l2" style="background:#27b567; --glow:#27b56755; animation-delay:.3s;" onclick="toggle(2)">
          <div class="layer-num">2</div>
          <div class="layer-name">Data Link</div>
          <div class="layer-proto tw" id="p2">Ethernet · Wi-Fi · PPP · MAC</div>
        </div>
        <div class="layer" id="l1" style="background:#1a8cd8; --glow:#1a8cd855; animation-delay:.35s;" onclick="toggle(1)">
          <div class="layer-num">1</div>
          <div class="layer-name">Physical</div>
          <div class="layer-proto tw" id="p1">USB · DSL · 802.11 · Fiber</div>
        </div>

        <!-- Detail panel -->
        <div class="detail-panel" id="detail"></div>

        <!-- Legend -->
        <div class="legend">
          <div style="display:flex;align-items:center;gap:5px;">
            <div class="legend-dot"></div>
            <span>Data packet traveling up</span>
          </div>
          <span>·</span>
          <span>Click any layer to explore</span>
        </div>
      </div>

      <!-- Right arrows -->
      <div style="width:30px; flex-shrink:0; display:flex; flex-direction:column; gap:5px;">
        <div style="height:60px; display:flex; align-items:center; justify-content:center;">
          <svg width="14" height="60" viewBox="0 0 14 60"><path d="M7 0 L7 50 L2 42 M7 50 L12 42" stroke="#7b2ff7" stroke-width="2" fill="none" stroke-linecap="round"/></svg>
        </div>
        <div style="height:60px; display:flex; align-items:center; justify-content:center;">
          <svg width="14" height="60" viewBox="0 0 14 60"><path d="M7 0 L7 50 L2 42 M7 50 L12 42" stroke="#d63af9" stroke-width="2" fill="none" stroke-linecap="round"/></svg>
        </div>
        <div style="height:60px; display:flex; align-items:center; justify-content:center;">
          <svg width="14" height="60" viewBox="0 0 14 60"><path d="M7 0 L7 50 L2 42 M7 50 L12 42" stroke="#f74e8e" stroke-width="2" fill="none" stroke-linecap="round"/></svg>
        </div>
        <div style="height:60px; display:flex; align-items:center; justify-content:center;">
          <svg width="14" height="60" viewBox="0 0 14 60"><path d="M7 0 L7 50 L2 42 M7 50 L12 42" stroke="#f9771e" stroke-width="2" fill="none" stroke-linecap="round"/></svg>
        </div>
        <div style="height:60px; display:flex; align-items:center; justify-content:center;">
          <svg width="14" height="60" viewBox="0 0 14 60"><path d="M7 0 L7 50 L2 42 M7 50 L12 42" stroke="#e8b800" stroke-width="2" fill="none" stroke-linecap="round"/></svg>
        </div>
        <div style="height:60px; display:flex; align-items:center; justify-content:center;">
          <svg width="14" height="60" viewBox="0 0 14 60"><path d="M7 0 L7 50 L2 42 M7 50 L12 42" stroke="#27b567" stroke-width="2" fill="none" stroke-linecap="round"/></svg>
        </div>
        <div style="height:60px; display:flex; align-items:center; justify-content:center; opacity:.3;">
          <svg width="14" height="60" viewBox="0 0 14 60"><path d="M7 0 L7 50 L2 42 M7 50 L12 42" stroke="#1a8cd8" stroke-width="2" fill="none" stroke-linecap="round"/></svg>
        </div>
      </div>
    </div>
  </div>

  <script>
    const data = {
      7: {
        color:'#7b2ff7', light:'#ede0ff',
        name:'Application layer',
        desc:'The closest layer to the end user. This is where apps like your browser, email client, or FTP tool live. It defines the rules for how applications request and exchange data — what language the software speaks.',
        protocols:['HTTP','HTTPS','DNS','FTP','SMTP','SSH','POP3','SNMP'],
        pdu:'Data (message)',
        example:'You type google.com — the browser sends an HTTP GET request from this layer.'
      },
      6: {
        color:'#d63af9', light:'#fae0ff',
        name:'Presentation layer',
        desc:'The translator. It converts data between the format the application uses and the format the network can understand — handling encryption, compression, and encoding. Think of it as the diplomat between apps and the network.',
        protocols:['TLS','SSL','JPEG','MPEG','ASCII','UTF-8','XDR'],
        pdu:'Data',
        example:'TLS encrypts your data here before it travels. JPEG compresses image data.'
      },
      5: {
        color:'#f74e8e', light:'#ffe0ef',
        name:'Session layer',
        desc:'Opens, manages, and closes sessions (conversations) between applications. It makes sure that if a connection drops mid-transfer, the session can be re-established — like a phone call you can resume after losing signal.',
        protocols:['NetBIOS','RPC','SIP','PPTP','L2TP','H.245'],
        pdu:'Data',
        example:'A video call stays in sync even if packets are delayed — session layer handles checkpoints.'
      },
      4: {
        color:'#f9771e', light:'#fff0e0',
        name:'Transport layer',
        desc:'Responsible for end-to-end delivery and reliability. TCP breaks data into segments, numbers them, confirms delivery, and reassembles them in order. UDP skips handshakes and just fires — great for speed over perfection.',
        protocols:['TCP','UDP','SCTP','QUIC','DCCP'],
        pdu:'Segment (TCP) / Datagram (UDP)',
        example:'Loading a webpage = TCP. Watching live video = UDP. Port numbers live here.'
      },
      3: {
        color:'#e8b800', light:'#fffbe0',
        name:'Network layer',
        desc:'Routes packets across different networks. IP addresses live here — this is where your data finds its path from your laptop in Charlotte to a server in Tokyo, hopping through routers along the way.',
        protocols:['IPv4','IPv6','ICMP','OSPF','BGP','RIP','ARP'],
        pdu:'Packet',
        example:'Your router uses IP routing tables at this layer. Ping uses ICMP (also layer 3).'
      },
      2: {
        color:'#27b567', light:'#e0fff0',
        name:'Data Link layer',
        desc:'Handles node-to-node transfer on the same physical network. MAC addresses live here — it frames the raw bits into structured chunks and handles collision detection. Wi-Fi and Ethernet are data link protocols.',
        protocols:['Ethernet','Wi-Fi (802.11)','PPP','HDLC','MAC','VLAN','ARP'],
        pdu:'Frame',
        example:'Your NIC card has a MAC address. ARP maps IPs to MACs at this layer.'
      },
      1: {
        color:'#1a8cd8', light:'#e0f2ff',
        name:'Physical layer',
        desc:'The actual hardware. Bits are converted to electrical signals, light pulses, or radio waves. It defines cables, connectors, voltages, and timing — the physical medium that carries everything else above it.',
        protocols:['USB','DSL','ISDN','Fiber Optic','Bluetooth','802.11 PHY','RS-232'],
        pdu:'Bit',
        example:'The ethernet cable or Wi-Fi radio transmitting raw bits. Fiber optic uses light pulses here.'
      }
    };

    let activeLayer = null;

    function toggle(n) {
      const d = data[n];
      const panel = document.getElementById('detail');
      const layers = document.querySelectorAll('.layer');

      if (activeLayer === n) {
        panel.classList.remove('visible');
        panel.innerHTML = '';
        document.getElementById('l'+n).classList.remove('active');
        activeLayer = null;
        return;
      }

      layers.forEach(l => l.classList.remove('active'));
      document.getElementById('l'+n).classList.add('active');
      activeLayer = n;

      const tags = d.protocols.map(p =>
        `<span class="tag" style="background:${d.color}22; color:${d.color}; border:1px solid ${d.color}44;">${p}</span>`
      ).join('');

      panel.style.background = d.light + '18';
      panel.style.borderColor = d.color + '44';
      panel.innerHTML = `
        <div class="detail-title" style="color:${d.color}">${d.name}</div>
        <div class="detail-desc">${d.desc}</div>
        <div style="margin-bottom:8px;">${tags}</div>
        <div class="example-row"><span style="color:${d.color}">PDU:</span> ${d.pdu}</div>
        <div class="example-row" style="margin-top:4px;"><span style="color:${d.color}">Real-world:</span> ${d.example}</div>
      `;
      panel.classList.add('visible');

      const el = document.getElementById('p'+n);
      el.classList.remove('run');
      void el.offsetWidth;
      el.classList.add('run');
    }

    // Packet animation
    const pkt = document.getElementById('pkt');
    const layerEls = [1,2,3,4,5,6,7].map(n => document.getElementById('l'+n));
    const colors = ['#1a8cd8','#27b567','#e8b800','#f9771e','#f74e8e','#d63af9','#7b2ff7'];
    const pktDelay = 420;

    function animatePacket() {
      function step(i) {
        if (i > 6) {
          pkt.style.opacity = '0';
          setTimeout(() => {
            pkt.style.transition = 'none';
            pkt.style.top = (layerEls[0].offsetTop + layerEls[0].offsetHeight / 2) + 'px';
            setTimeout(() => {
              pkt.style.transition = 'top 0.35s cubic-bezier(.4,0,.2,1), opacity 0.3s';
              step(0);
            }, 60);
          }, 600);
          return;
        }
        const el = layerEls[i];
        const center = el.offsetTop + el.offsetHeight / 2;
        pkt.style.transition = 'top 0.35s cubic-bezier(.4,0,.2,1), opacity 0.3s';
        pkt.style.top = center + 'px';
        pkt.style.opacity = '1';
        pkt.style.background = colors[i];
        setTimeout(() => step(i + 1), pktDelay);
      }

      pkt.style.top = (layerEls[0].offsetTop + layerEls[0].offsetHeight / 2) + 'px';
      pkt.style.opacity = '0';
      step(0);
    }

    setTimeout(animatePacket, 800);
  </script>
</body>
</html>
