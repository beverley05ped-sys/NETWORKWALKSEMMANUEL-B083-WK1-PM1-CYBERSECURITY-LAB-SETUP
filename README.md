# NETWORKWALKSEMMANUEL-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP
## Cybersecurity Lab Setup - Week 1 | NetworkWalks

**Student:** Emmanuel | **Batch:** B083 | **Week:** WK1-PM1
**Lab:** Cybersecurity Lab Setup with VirtualBox + Kali Linux
**Sample Reference:** https://github.com/waqaskarimccie/Cybersecurity-Lab-Setup1

### Objective
Setup an isolated cybersecurity lab for hands-on ethical hacking practice.

### Tools Used
- Oracle VirtualBox 7.x
- Kali Linux 2026.3 (virtualbox-amd64.vdi) - 80.09 GB Virtual / 15.67 GB Actual
- Windows 11 Host - Kimberley, South Africa
- 7-Zip, GitHub

### Setup Steps & Issues Solved

**1. Download & Extract**
Downloaded Kali VBox image, extracted to C:\Kali to avoid long path issues.

**2. Issue #1 - VERR_FILE_NOT_FOUND**
Error: Failed to open image file in C:\Users\Admin\AppData\Local\Temp\...
Root Cause: File extracted to Temp and Windows blocked it.
Fix: Moved .vdi to C:\Kali, Right-click > Properties > Unblock > Apply.

**3. Issue #2 - E_FAIL (0x80004005) UUID Conflict**
Error: Cannot register hard disk {uuid} because a hard disk with UUID already exists in Temp.
Root Cause: Old Temp file still registered in VirtualBox Media Manager.
Fix: File > Tools > Virtual Media Manager > Selected old entries with yellow triangle > Release > Remove > Then re-added C:\Kali\kali-linux-2026.3-virtualbox-amd64.vdi

**4. Boot & Login**
Attached disk to SATA Controller Port 0, Started VM.
Login: kali / kali - Successful to Kali Dragon Desktop.

**5. Update**
Command: `sudo apt update && sudo apt upgrade -y`
Result: 298 packages updated, including chromium, libtalloc2, clang-tools, llvm-21 at 1401 kB/s.

### Screenshots
(Screenshots folder contains evidence of all steps)
- VERR_FILE_NOT_FOUND error
- UUID conflict error
- Virtual Media Manager healthy disk (80.09 GB)
- Kali login and desktop
- Terminal update 51%

### Verification
- Kali VM boots correctly
- Internet works
- Terminal commands working
- Snapshot taken as "Fresh Install" for rollback

### Learnings
VirtualBox keeps its own registry. Deleting file is not enough, you must remove from Virtual Media Manager. Also always extract to short path like C:\Kali, not Temp.

### Next Week
Add Ubuntu Server victim, Install Guest Additions, Setup NAT Network, Install Wazuh/Wireshark.
