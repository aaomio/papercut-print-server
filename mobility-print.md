# Mobility Print Setup

## Overview

Mobility Print is used to provide printer deployment for BYOD devices without requiring manual driver installation or domain join. It allows users to install printers through a web-based setup portal and connects them into the existing PaperCut NG print workflow.

---

## Installation

Mobility Print is installed on the print server (Matrix-PS-01).

### Step 1: Download and install
- Download Mobility Print from [Official Download Page](https://www.papercut.com/products/mf/mobility-print/download/server/)
- Run the installer on Matrix-PS-01
- Complete installation using default settings unless specified otherwise

### Step 2: Service verification
- Confirm Mobility Print service is running on Matrix-PS-01
- Ensure the server is reachable on port 9163 (`http://localhost:9163/login`)

---

## Setup Portal

The Mobility Print setup portal is used to deploy printers to client devices.

Access:

http://Matrix-PS-01:9163/setup

### Functionality
- Detects client operating system
- Provides correct printer package for installation
- Installs FollowMe printer automatically on client devices

