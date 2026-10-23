# First-Time GitHub Setup (Beginner Friendly)

## Recommended repository

**Name:** `piezo-vibration-analog-front-end`  
**Description:** `Design and LTspice validation of an AD8608 piezoelectric vibration-sensor front end, progressing toward PCB fabrication.`  
**Visibility:** Public for portfolio use, after checking screenshots/files for sensitive information.  
**Topics:** `ltspice`, `analog-electronics`, `piezoelectric-sensor`, `charge-amplifier`, `circuit-design`, `pcb-design` (last topic represents project direction, not a completed PCB).

## Path A — Recommended: GitHub Desktop

1. Extract this starter-pack ZIP.
2. Keep the included README/docs/media and **copy your real `.asc` file from Windows** into `03_LTspice/`.
3. Open [GitHub Desktop](https://desktop.github.com/), sign in, and choose `File → Add Local Repository...` or `File → New Repository...` depending on whether the folder has been initialized already.
4. If the folder is not a Git repository yet, let GitHub Desktop **create a repository here**. Do not accidentally make a second nested folder.
5. Check the changed-file list; verify no huge `.raw` or sensitive files are being added.
6. Commit with the message `docs: initialize vibration sensor AFE portfolio`.
7. Choose **Publish repository**, set repository name, select public if appropriate, then publish.
8. Open the URL that GitHub Desktop gives you and check README images.

Official GitHub Desktop guide: https://docs.github.com/en/desktop/adding-and-cloning-repositories/adding-a-repository-from-your-local-computer-to-github-desktop

## Path B — Git commands (alternative)

Create a **new empty repository on GitHub** named `piezo-vibration-analog-front-end` without initializing extra README, license or gitignore files. In a terminal opened inside the extracted folder:

```bash
git init -b main
git add .
git commit -m "docs: initialize vibration sensor AFE portfolio"
git remote add origin YOUR_ACTUAL_GITHUB_REPOSITORY_URL
git push -u origin main
```

Use a real repository URL, and sign into GitHub through your chosen Git authentication method.

Official guide: https://docs.github.com/en/migrations/importing-source-code/using-the-command-line-to-import-source-code/adding-locally-hosted-code-to-github

## Updating after a new simulation

- Edit the relevant `*.md` document and add the revised `.asc` and screenshot.
- In GitHub Desktop, review changes and commit `sim: [specific completed test]`.
- Click **Push origin**.
- Keep LinkedIn Projects pointing to the same repository URL.

## LinkedIn setup

Go to **View Profile → Add profile section → Recommended → Projects** and paste `LinkedIn/Project_Entry.md`. Set **October 2026** as the start date; leave the end date blank while active. Add GitHub with **Media → Add a link**. Official guide: https://www.linkedin.com/help/linkedin/answer/a8064614
