# PaperCut Client (PC-Client Deployment)

## Overview

The PaperCut Client is deployed to end-user devices to provide authentication pop-ups, user identification, and real-time interaction with PaperCut NG. It ensures that print jobs are correctly attributed to the logged-in user and enables features such as account balance display, print notifications, and authentication prompts.

---

## SMB Deployment

The PaperCut Client installer is shared from the print server.

### Access

\\Matrix-PS-01\PCClient

### Steps

- Open File Explorer on the client device  
- Enter the SMB path above  
- Locate the PCClient installer from the relevant OS folder
- Run the installer on the client machine  
- Complete installation using default settings  

---

## Functionality

Once installed, the PaperCut Client provides:

- Automatic user authentication based on Active Directory login  
- Pop-up notifications for print job confirmation  
- Display of user balance or quota (if enabled)   

---

## Authentication Behaviour

When a user sends a print job:

- a login prompt is displayed  
- Credential is verified by PaperCut NG  
- Job then goes to release queue
