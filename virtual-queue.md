# Virtual Queue (FollowMe)

## Overview

The virtual queue provides the central entry point for all print jobs in this environment. It is implemented as a Windows printer configured with a `NUL:` port, ensuring that print jobs are not sent directly to a physical device.

All submitted jobs are intercepted and managed by PaperCut NG for authentication, tracking, and routing decisions.

---

## Purpose

The virtual queue is used to:

- Centralise all print job submissions
- Support FollowMe-style printing workflows

---

## Configuration (Windows Print Server)

The virtual queue is created on Matrix-PS-01.

### Step 1: Create printer
- Win+R and Enter `printmanagement.msc`
- Add new printer on the print server

### Step 2: Configure port
- Select existing port
- Choose `NUL:` port

### Step 3: Install driver
- Use the standard printer driver installed for the printer

### Step 4: Share printer
- Enable sharing
- Share name: FollowMe
- Ensure SMB access is available via `\\Matrix-PS-01\FollowMe`

---

## PaperCut NG Configuration (Port 9191)

After creating the printer, it must be configured in PaperCut NG.

Access:

http://localhost:9191/admin

### Step 1: Printer visibility
- Confirm FollowMe appears under Printers and Open FollowMe printer settings

### Step 2: Virtual queue configuration
- Set queue type as **This is a Virtual queue**
- Set **Job Redirection Settings** with physical printer queues

### Step 3: Enable Hold and Release
- Enable hold/release printing

---

## Mobility Print Configuration (Port 9163)

Access:

http://Matrix-PS-01:9163/admin

### Step 1: Printer publishing
- Ensure only FollowMe is published

### Step 2: Authentication
- Ensure users must authenticate before installing printers
