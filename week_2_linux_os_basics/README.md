# Week 2 – Linux Operating System Basics (Kali / Apporto)

This week builds on Linux fundamentals essential for cybersecurity work. The focus was on navigating the Linux filesystem, managing files, using redirection, editing with Nano, exploring network configuration, and using sudo privileges.  
(Reference: Week‑2 LAB screenshots) [1](https://stulsbuac-my.sharepoint.com/personal/s4418500_lsbu_ac_uk/_layouts/15/Doc.aspx?sourcedoc=%7B9B9EB08E-33C6-4499-B45B-71772EECDD8F%7D&file=Week-2%20LAB%20screen%20shots.docx&action=default&mobileredirect=true)

---

## 1. Navigation Commands

### pwd — Print Working Directory  
`pwd` shows the absolute path of the current directory (e.g., `/home/kali/Desktop`).  
This prevents executing commands in the wrong location.

### ls and ls -a  
- `ls` → visible files  
- `ls -a` → includes hidden files  
Hidden files (beginning with `.`) often contain configuration or credentials.

### cd — Change Directory  
Examples:

cd Desktop
cd /
cd ..

`/` is the **root**, containing all system-critical directories (`/etc`, `/usr`, `/var`, `/home`).

---

## 2. File Creation & Editing

### touch  
touch file1.txt
Creates an empty file.

### cat  
- `cat file.txt` → view  
- `cat > file.txt` → overwrite  
- `cat >> file.txt` → append

### echo 
echo "hello" > log.txt

### Nano Editor
nano file3
Save with **CTRL+O**, exit with **CTRL+X**.

Created Python script:
nano file4.py
print("Hello World")
---

## 3. Network Commands & Sudo

### ifconfig  
Shows IP, MAC, interface state.

### sudo  
Used to create root-owned file:
sudo nano securefile
Attempting to edit without sudo produced *permission denied*, demonstrating Linux access control.

**Security relevance:**  
- Prevents unauthorized changes  
- Limits administrative privileges  
- Logs privileged actions  
- Protects sensitive files from normal users

---

## 4. Exercises

### Exercise 1 — Explore Root Directory  
cd /
ls /
Color meanings:
- Blue → directories  
- White → regular files  
- Green → executables  
- Cyan → symbolic links

### Exercise 2 — Codes Folder & Safe Copy 
mkdir ~/Documents/Codes
cp -un ~/Desktop/file4.py ~/Documents/Codes
cp -un ~/Desktop/file5.py ~/Documents/Code
`-u` = copy only newer files  
`-n` = do not overwrite

### Exercise 3 — sudo vs root  
Root = unrestricted power.  
Sudo = temporary elevation (safer).  
Operating as root exposes system-wide risk.

---

## Evidence  
- Screenshots: `screenshots/`  
- Full document: `docs/Week_2_LAB_screenshots.docx`
