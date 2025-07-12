# 🗃 Personal Data Export Checklist

> Goal: Get all key data exported in human-readable, portable formats.
# ✅ Personal Data Export Checklist (Explicit Exports Only)

This list includes only data that is **not safely handled by regular disk backups** and must be **explicitly exported** to ensure long-term readability, portability, and completeness.

---

## 🧳 1. Google Takeout

- [x] Export data via [takeout.google.com](https://takeout.google.com)
Select only what you use. Recommended sections:

#### 📬 Gmail
- [ ] Export `.mbox` file (ensure it’s non-empty)
- [ ] Confirm it contains **Sent mail**, **All Mail**, and **important folders**
- [ ] Labels appear as metadata or in folder names
- [ ] File is readable in Thunderbird or other MBOX viewer

#### 📁 Google Drive
- [ ] Export files in **PDF**, **ODT**, or **original formats**
- [ ] Ensure Docs, Sheets, and Slides are converted and usable
- [ ] Confirm embedded images/media are included
- [ ] Folder structure is preserved (or recoverable)

#### 👥 Contacts
- [ ] Export as `.vcf` (vCard)
- [ ] Check that contact names, emails, phone numbers are intact
- [ ] Verify importability into another contact manager (e.g. Thunderbird, KDE Contacts)

#### 📅 Calendar
- [ ] Export as `.ics`
- [ ] Confirm event titles, times, locations, and attendees are present
- [ ] Check timezones and recurring events are handled correctly

#### 🖼 Google Photos
- [ ] Download original-quality images + JSON metadata
- [ ] Confirm filenames match and metadata (dates, captions) exists
- [ ] Verify album structure if preserved

---

## 🔐 2. Password Manager Backup

### [ ] Export encrypted vault file

- [ ] Format: `.kdbx` (KeePassXC), encrypted `.json` or `.csv` (Bitwarden, 1Password)
- [ ] Check that the file includes:
  - [ ] All accounts
  - [ ] Notes and fields (TOTP seeds, recovery codes)
  - [ ] Folder or tag structure (if applicable)
- [ ] Securely store the **master password** or keyfile
- [ ] NEVER export in plaintext unless encrypted at rest

---

## 💬 3. Messaging Apps

### WhatsApp
- [ ] Use "Export Chat" feature to `.txt` (with media optional)
- [ ] Ensure timestamps, sender names, and content are present
- [ ] Save as `whatsapp-export-<chatname>.txt`

### Signal
- [ ] Use backup feature (creates `.backup` file)
- [ ] Ensure you have the **32-digit restore passphrase**
- [ ] Note: not readable without restoring in Signal

### iMessage
- [ ] Use Mac with `iMazing`, `iExplorer`, or native backup
- [ ] Check message threads, timestamps, and media are exported

### Others (Telegram, Discord)
- [ ] Use built-in data export if available
- [ ] Confirm that private DMs and channel data are included
- [ ] Save exported JSON, HTML, or text

---

## 🌍 4. Browser Data

### [ ] Export Bookmarks
- [ ] Format: `.html`
- [ ] Check folder structure and labels preserved
- [ ] Open file in browser to verify usability

### Export History or Sessions
- [ ] May require a browser extension or profile inspection
- [ ] Ensure you’re not just relying on proprietary formats in `~/.config`

---

## 🖥 5. System Metadata

- [ ] Dump install and service state

```bash
mkdir -p ~/Archive/system
dnf list installed > ~/Archive/system/packages.txt
systemctl list-units > ~/Archive/system/services.txt
uname -a > ~/Archive/system/uname.txt
