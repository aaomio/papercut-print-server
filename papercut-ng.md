# PaperCut NG Setup

## Overview

PaperCut NG is the central print management system used in this environment. It provides user authentication, print job tracking, quota enforcement, and secure print release functionality. It integrates directly with the Windows Print Server and Active Directory to ensure all print activity is tied to authenticated domain users.

---

## Installation

PaperCut NG is installed on the print server (Matrix-PS-01).

### Step 1: Prepare the server
- Ensure Matrix-PS-01 is joined to the Active Directory domain
- Confirm DNS resolution to the domain controller is working

### Step 2: Install PaperCut NG
- Download PaperCut NG from [official download page](https://www.papercut.com/products/ng/download/)
- Run the installer on Matrix-PS-01
- Select **Application Server installation**
- Complete installation using default configuration

### Step 3: Verify services
After installation, confirm the following services are running:

- PaperCut Application Server
- PaperCut Print Provider

These services enable web admin access and print queue monitoring.

---

## Active Directory Integration

### Step 1: Enable domain connection
- Open PaperCut Admin interface (`http://localhost:9191/admin`)
- Navigate to **Options\User/Group Sync**
- Select Active Directory as the user source

### Step 2: Configure domain sync
- Enter domain: `matrix.local`
- Provide domain credentials with read access to AD
- Run initial user sync

### Step 3: Verify user import
- Confirm users from Active Directory appear in PaperCut
- Validate test user (e.g. Neo) exists in the user list

### Step 4: Policy readiness
Once synced, users can be used for:

- Print job tracking
- Authentication during release
- Group-based restrictions and quotas

---

## Printer Monitoring

PaperCut NG monitors selected print queues on the print server. 

- Virtual FollowMe queue (central job intake point)
- Physical printer queues (colour and mono output queues)

The virtual queue is configured as the primary interception point for all print jobs before routing decisions are applied by PaperCut NG.

---

## Hold and Release Workflow

All jobs sent to the FollowMe queue are held by default. Jobs are not printed immediately.

The workflow is:

1. User submits print job
2. PaperCut intercepts the job
3. Job is placed in held state
4. User authenticates using Active Directory credentials
5. Job appears in the release interface
6. User selects release destination
7. Job is forwarded to the physical printer queue

---

## Services

The following services must be running:

- PaperCut Application Server
- PaperCut Print Provider

If either service is stopped, print job tracking and interception will fail.

