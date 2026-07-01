# PaperCut Client Access

## Overview

Client printing is supported through three methods: SMB shared printing, Mobility Print (BYOD), and Web Print. All methods route jobs into the FollowMe virtual queue, where PaperCut NG applies authentication, tracking, and release control.

---

## 1. SMB Shared Printing (Domain Devices)

Domain-joined devices connect directly to shared printers hosted on the print server.

### Access

\\Matrix-PS-01\FollowMe

### Steps

- Open File Explorer  
- Enter the SMB path above  
- Authenticate using Active Directory credentials if prompted  
- Install the FollowMe printer  
- Submit print jobs normally  

---

## 2. Mobility Print (BYOD Devices)

Non-domain devices install printers using the Mobility Print setup portal.

### Access

http://Matrix-PS-01:9163/setup

### Steps

- Open the setup portal in a browser  
- Select operating system  
- Download and install printer package  
- FollowMe printer is automatically added  
- Use installed printer for printing  

---

## 3. Web Print (Browser-Based)

Web Print allows document submission directly from a browser without installing printers.

### Access

http://Matrix-PS-01:9191/user

### Steps

- Log in using Active Directory credentials  
- Navigate to Web Print section  
- Upload document  
- Submit print job to FollowMe queue  

---

## Common Print Flow (All Methods)

Regardless of method used, all print jobs follow the same backend process:

- Job is sent to FollowMe virtual queue  
- PaperCut NG intercepts the job  
- Job is placed in held state  
- User authentication is applied if required  
- Job appears in release interface  
- User releases job on the physical printer  
