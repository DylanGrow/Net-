# OSI Model Interactive Visualizer

A high-performance, single-page web application designed to visualize the 7-layer Open Systems Interconnection (OSI) model. This tool serves as a technical reference for understanding data encapsulation and protocol distribution across the network stack.

## 🖥️ Application Overview

The page provides a structural representation of the networking stack, allowing for deep exploration of each layer's functionality and its role in end-to-end communication.

### Key Functional Areas

* **Interactive Reference Stack:** A vertical representation of the seven layers. Selecting any layer dynamically expands a detailed panel containing technical specifications, including the specific Protocol Data Unit (PDU) and a comprehensive list of associated protocols.
* **Encapsulation Visualization:** A synchronized animation simulates a data packet traveling up the stack from the Physical layer to the Application layer, visually demonstrating how data moves through hardware and software.
* **Protocol Mapping:** Each layer includes a curated list of modern protocols (such as QUIC, TLS, and BGP) represented as categorized tags for rapid identification.
* **Contextual Real-World Examples:** The application provides practical scenarios for each layer—such as HTTP GET requests at the Application layer or MAC address mapping at the Data Link layer—to bridge the gap between theory and practice.

## 🎨 Design & User Experience

* **Responsive Architecture:** The layout is optimized for high-density displays and adjusts seamlessly across different screen dimensions.
* **Technical Aesthetics:** Built with a dark-mode interface, utilizing color-coded layer accents to maintain visual distinction between different parts of the stack.
* **Motion Design:** Uses fluid transitions and subtle animations to enhance readability and user engagement during exploration.

## 🎯 Intended Use

This project is intended as a quick-access educational tool for troubleshooting network concepts, preparing for technical interviews, or demonstrating the flow of data across the standard networking model.
