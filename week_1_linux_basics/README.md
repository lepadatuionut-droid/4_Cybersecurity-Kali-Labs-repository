# Week 1 – Linux CLI Essentials (Kali / Apporto)

**Focus:** Practical Linux terminal fundamentals used in cybersecurity workflows:
- Directory & file operations (`mkdir`, `touch`, `cp`, `mv`, `rm`, `rm -r`, `rmdir`)
- Handling absolute paths in Kali (using `/home/kali/...` when `~` is not available)
- Absolute paths on Kali when `~` is unavailable (use `/home/kali/...`)
- Quoting/escaping names with spaces (`"command line"` or `command\ line`)
- Exporting terminal history (`history > my_history.txt`)
- Packaging artifacts as a ZIP for evidence and download

## Artifacts for Week 1
- Report (DOCX): [`docs/Week_1_LAB_work_report.docx`](./docs/Week_1_Lscreenshots/`](./screensolder (example files/dirs): [`command_line/`- Downloadable ZIP (root archives): `../archives/week_1_Tutorial.zip`

## What’s inside this week
- `command_line/` – working directory used during the lab
- `docs/Week_1_LAB_work_report.docx` – full lab write‑up
- `screenshots/` – selected terminal/desktop screenshots
- `archives/` – exported artifact (zip) for download

## Evidence Map (Week 1)

- **CLI Fundamentals:** `command_line/` (created/moved/copied/removed files & folders; handled spaces; used absolute paths)
- **History Export:** `command_line/my_history.txt` (commands captured for audit/evidence)
- **Reproducible Artifact:** `../archives/week_1_Tutorial.zip` (packaged outputs)
- **Documentation:** `docs/Week_1_LAB_work_report.docx` (full write‑up with screenshots)

## Notes & Lessons Learned

  **Typing `~` (tilde) in Apporto/Kali:** Some keyboard layouts or the Apporto web client make it hard to enter `~`.  
  **Fix:** Replace `~` with the absolute path to the home directory:
  - For Kali’s default user → use `/home/kali/...`
  - You can also use the environment variable `$HOME/...`
  - Example: `cd ~/Documents` ⇢ `cd /home/kali/Documents` or `cd $HOME/Documents`

- **GUI vs. Terminal vs. Apporto Files panel (different views):**  
  The Kali file manager (inside the VM) and the Apporto **Files** panel (browser sidebar) may not show the same filesystem mount points. The **terminal** (`pwd`, `ls -la`) is the source of truth.
  
  **Workflows that always worked:**
  - Export from the terminal to a known location (e.g., `/home/kali/Desktop/week_1_Tutorial.zip`)
  - If the Files panel doesn’t show Desktop, copy the file into a panel‑visible folder (e.g., `/home/kali/Downloads`) with `cp`.
  - As a fallback, upload the ZIP directly to GitHub **from inside the VM browser**.

- **Moving a file *into* a directory vs. renaming a file:**  
  `mv homeworkfile linux.lunches` will **rename** the file if `linux.lunches` does **not** exist as a directory.
  
  **Best practice:** Ensure the target directory exists and use a trailing slash to show intent:
  ```bash
  mkdir -p linux.lunches
  mv homeworkfile linux.lunches/   # clearly “into” the directory

