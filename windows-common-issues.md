# Windows Common Issues — Troubleshooting Guide

## 1. Computer Running Slowly

**Symptoms:** System is sluggish, apps take long to open, high CPU/RAM usage.

**Steps:**
1. Open Task Manager (`Ctrl + Shift + Esc`) → check CPU, Memory, Disk usage
2. End any unnecessary high-usage processes
3. Run Disk Cleanup: `Start → Disk Cleanup → select C: drive`
4. Disable startup programs: Task Manager → Startup tab → disable unnecessary items
5. Check for Windows Updates: `Settings → Windows Update → Check for updates`
6. Restart the machine if not done recently
7. If issue persists, consider increasing virtual memory or upgrading RAM

---

## 2. Blue Screen of Death (BSOD)

**Symptoms:** System crashes with a blue screen and error code.

**Steps:**
1. Note the error code displayed (e.g. `SYSTEM_THREAD_EXCEPTION_NOT_HANDLED`)
2. Restart and check if it was a one-time occurrence
3. Run Windows Memory Diagnostic: `Start → Windows Memory Diagnostic`
4. Check Event Viewer for crash logs: `Start → Event Viewer → Windows Logs → System`
5. Update or roll back recently installed drivers
6. Run `sfc /scannow` in Command Prompt (Admin) to repair system files
7. Escalate to senior technician if BSOD recurs after steps above

---

## 3. Unable to Log In to Windows

**Symptoms:** User cannot log in — wrong password, account locked, or profile error.

**Steps:**
1. Confirm the user is typing the correct username and password (check Caps Lock)
2. If domain-joined: check network connectivity — user may not be able to reach the domain controller
3. If account is locked: unlock via Active Directory Users and Computers (admin access required)
4. If password expired: reset via AD or self-service portal
5. If profile is corrupted: log in with a temporary profile and back up user data
6. Escalate to AD admin if account issues cannot be resolved locally

---

## 4. Printer Not Working

**Symptoms:** Printer offline, not printing, or print jobs stuck in queue.

**Steps:**
1. Check physical connections — USB or network cable, power on
2. Verify printer is set as Default Printer: `Settings → Printers & Scanners`
3. Clear print queue: `Control Panel → Devices and Printers → right-click printer → See what's printing → Cancel all`
4. Restart Print Spooler service: `services.msc → Print Spooler → Restart`
5. Remove and re-add the printer
6. Reinstall printer drivers from manufacturer's website if issue persists

---

## 5. Windows Update Failing

**Symptoms:** Updates stuck, failing with error codes, or not downloading.

**Steps:**
1. Run Windows Update Troubleshooter: `Settings → Troubleshoot → Windows Update`
2. Clear Windows Update cache:
   - Stop Windows Update service: `net stop wuauserv`
   - Delete contents of `C:\Windows\SoftwareDistribution\Download`
   - Restart service: `net start wuauserv`
3. Check disk space — ensure at least 10GB free on C: drive
4. Run `sfc /scannow` to check for corrupted system files
5. Try updating via Windows Update Assistant if standard update fails

---

## 6. Application Crashes or Won't Open

**Symptoms:** App closes unexpectedly or fails to launch.

**Steps:**
1. Restart the application
2. Restart the computer
3. Check Event Viewer for application error logs: `Event Viewer → Windows Logs → Application`
4. Repair or reinstall the application
5. Ensure the app is compatible with the current Windows version
6. Check if a recent Windows Update caused the issue — consider rollback if confirmed

---

*Last updated: July 2026*
