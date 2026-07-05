# Microsoft 365 Issues — Troubleshooting Guide

## 1. Outlook Not Receiving Emails

**Symptoms:** Emails not arriving, inbox not updating.

**Steps:**
1. Check internet connectivity
2. Verify Outlook is not in Offline Mode: `Send/Receive tab → Work Offline` (should be unchecked)
3. Check Junk/Spam folder
4. Check if mailbox is full: `File → Account Settings → check mailbox size`
5. Remove and re-add the email account
6. Check Microsoft 365 Service Health at `admin.microsoft.com` for outages
7. Escalate to admin if server-side issue suspected

---

## 2. Outlook Keeps Asking for Password

**Symptoms:** Repeated password prompts even after entering correct credentials.

**Steps:**
1. Check if password has recently changed — update credentials in Windows Credential Manager
2. Open Credential Manager: `Control Panel → Credential Manager → Windows Credentials`
3. Remove any saved Office/Outlook credentials and re-enter
4. Sign out and sign back in to Microsoft 365 account
5. Check if Multi-Factor Authentication (MFA) token has expired
6. Repair Office installation: `Control Panel → Programs → Microsoft 365 → Change → Quick Repair`

---

## 3. Microsoft Teams Not Loading / Crashing

**Symptoms:** Teams stuck on loading screen, crashes on launch, or calls dropping.

**Steps:**
1. Clear Teams cache:
   - Close Teams completely (check system tray)
   - Navigate to `%appdata%\Microsoft\Teams`
   - Delete contents of: `Cache`, `blob_storage`, `databases`, `GPUCache`, `IndexedDB`, `Local Storage`, `tmp`
   - Restart Teams
2. Check internet connection quality — Teams requires stable connection for calls
3. Sign out and sign back in
4. Update Teams to latest version
5. Reinstall Teams if issue persists

---

## 4. OneDrive Not Syncing

**Symptoms:** Files not syncing, sync errors, OneDrive icon showing red X or yellow warning.

**Steps:**
1. Click OneDrive icon in system tray → check for error messages
2. Pause and resume sync: `OneDrive icon → Pause syncing → Resume syncing`
3. Check available disk space — OneDrive needs local space to sync
4. Check file/folder names for invalid characters (`, *, :, ?, ", <, >, |, \`)
5. Sign out and sign back in to OneDrive
6. Reset OneDrive:
   ```
   %localappdata%\Microsoft\OneDrive\onedrive.exe /reset
   ```
7. Check file size limits — OneDrive has a 250GB per file limit

---

## 5. Cannot Access SharePoint / Permission Denied

**Symptoms:** User gets "Access Denied" when opening SharePoint site or document.

**Steps:**
1. Confirm user is signed in with the correct Microsoft 365 account
2. Check if the user has been granted access to the SharePoint site
3. Request site owner to check and grant permissions
4. Clear browser cache and cookies, try again
5. Try accessing from a different browser (Edge, Chrome)
6. Escalate to IT admin or SharePoint site owner to manage permissions

---

*Last updated: July 2026*
