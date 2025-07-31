# 🗃 Personal Data Export Checklist

> Goal: Get all key data exported in human-readable, portable formats.
# ✅ Personal Data Export Checklist (Explicit Exports Only)

This list includes only data that is **not safely handled by regular disk backups** and must be **explicitly exported** to ensure long-term readability, portability, and completeness.

---

## 🧳 1. Google Takeout

- [x] Export data via [takeout.google.com](https://takeout.google.com)
Select only what you use. Recommended sections:

#### 📬 Gmail
- [x] Export `.mbox` file (ensure it’s non-empty) 
- [x] Confirm it contains **Sent mail**, **All Mail**, and **important folders**
- [x] Labels appear as metadata or in folder names
- [x] File is readable in Thunderbird or other MBOX viewer

#### 📁 Google Drive
- [x] Export files in **PDF**, **ODT**, or **original formats**
- [x] Ensure Docs, Sheets, and Slides are converted and usable
- [x] Confirm embedded images/media are included
- [x] Folder structure is preserved (or recoverable)

#### 👥 Contacts
- [x] Export as `.vcf` (vCard)
- [x] Check that contact names, emails, phone numbers are intact
- [x] Verify importability into another contact manager (e.g. Thunderbird, KDE Contacts)

#### 📅 Calendar
- [x] Export as `.ics`
- [x] Confirm event titles, times, locations, and attendees are present
- [x] Check timezones and recurring events are handled correctly

#### 🖼 Google Photos
- [x] Download original-quality images + JSON metadata
- [x] Confirm filenames match and metadata (dates, captions) exists
- [x] Verify album structure if preserved

---

## 🔐 2. Password Manager Backup

### [ ] Export encrypted vault file

- [x] Format: `.kdbx` (KeePassXC), encrypted `.json` or `.csv` (Bitwarden, 1Password)
- [x] Check that the file includes:
  - [x] All accounts
  - [x] Notes and fields (TOTP seeds, recovery codes)
  - [x] Folder or tag structure (if applicable)
- [ ] Securely store the **master password** or keyfile
- [x] NEVER export in plaintext unless encrypted at rest

---

## 💬 3. Messaging Apps

### WhatsApp
- [x] Use "Export Chat" feature to `.txt` (with media optional)
- [x] Ensure timestamps, sender names, and content are present
- [x] Save as `whatsapp-export-<chatname>.txt`

### Signal
- [x] Use backup feature (creates `.backup` file)
- [x] Ensure you have the **32-digit restore passphrase**
- [x] Note: not readable without restoring in Signal
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
