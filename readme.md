# Windows Print Server with PaperCut NG and Mobility Print

Enterprise printing environment where users authenticate against a domain and submit print jobs through a controlled print server.

This project is built on top of an existing Windows Server Active Directory environment.

- [Windows Server Active Directory Lab](https://github.com/aaomio/win-server-AD)  
  Provides the base domain environment used for authentication, DNS, and client management.

- [Windows Print Server Lab](https://github.com/aaomio/win-print-server)  
Extends the Active Directory environment with Windows print services, shared printer deployment, and SMB access.


---

## Project Overview

This environment builds a complete Windows-based infrastructure consisting of:

- Active Directory domain controller for central authentication and user management  
- Windows print server for shared printer deployment and management  
- PaperCut NG for print tracking, authentication, and secure release printing  
- Mobility Print for BYOD printer deployment  
- Virtual FollowMe queue using a NUL: port for print job interception and routing  

---

## Software Downloads

- [PaperCut NG](https://www.papercut.com/products/ng/download/)

- [Mobility Print](https://www.papercut.com/products/mf/mobility-print/download/server/)

---

## Components

### PaperCut NG
- Print tracking
- User authentication
- Hold and release printing
- Print restrictions and quotas

### Mobility Print
- BYOD printer deployment
- Web-based printer installation

### Virtual Queue
- Windows printer using NUL: port
- Acts as FollowMe queue

### Windows Print Server
- Matrix-PS-01
- SMB printer sharing
- Driver management

### Active Directory
- User authentication source
- Domain and group based access control

---

## Documentation

- [PaperCut NG Setup](./papercut-ng.md)
- [Mobility Print Setup](./mobility-print.md)
- [Virtual Queue Setup](./virtual-queue.md)
- [PaperCut Client Access](./papercut-client.md)
- [Papercut Client App](./PC-client-exe.md)

---

## Features

### Authentication
- Active Directory login validation
- PaperCut user identity mapping

### Print Control
- Hold and release queues
- Job tracking per user
- Print restrictions

### Deployment
- SMB shared printers
- Mobility Print web deployment
- Automatic driver installation

### Virtual Printing
- Single FollowMe queue routing to multiple physical printers

