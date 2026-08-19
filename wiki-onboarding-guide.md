# Wiki Onboarding Guide

## What is Markdown?

Markdown is a lightweight way to format text using plain characters. Instead of clicking a "Bold" button, you type `**bold**`. Instead of inserting a heading from a menu, you type `# My Heading`.

Markdown files end in `.md` and look like plain text when opened in any editor, but render as formatted documents in Obsidian, GitHub, and most documentation sites.

A quick reference:

```
# Heading 1
## Heading 2

**bold text**
*italic text*

- bullet item
- another item

[link text](https://example.com)

![image alt text](path/to/image.png)
```

---

## Initial Setup

### Step 1 — Prerequisites: Git must be installed on your computer

Obsidian Git relies on the system Git binary to operate. Check whether Git is already installed before continuing.

**Mac:**  
Git is usually pre-installed. Open **Terminal** (press `Cmd+Space`, type `Terminal`, press Enter) and run:
```
git --version
```
If you see a version number (e.g. `git version 2.39.0`), you are ready. If you see an error or a prompt to install Xcode Command Line Tools, click **Install** and wait for it to finish.

**Windows:**  
Git is usually not installed by default. Download and run the installer from [git-scm.com/downloads](https://git-scm.com/downloads).

 After installing, you do not need to open Git again — Obsidian will use it automatically.

---

### Step 2 — Create a GitHub Personal Access Token

You need this token to authenticate with GitHub.

1. Go to [github.com/settings/tokens](https://github.com/settings/tokens)
2. Click **Generate new token → Generate new token (classic)**
5. Under **Select scopes**, check the box next to **repo** (this covers all permissions needed)
6. Scroll down and click **Generate token**
7. **Copy the token now** — GitHub only shows it once. Paste it into a text file or password manager temporarily.

---

### Step 3 — Install Obsidian

1. Go to [obsidian.md](https://obsidian.md) website and download and install the program
3. Open Obsidian — on the welcome screen, click **Create new vault**
4. Give the vault any name (e.g. `wiki`) and choose where to save it
5. Click **Create**

---

### Step 4 — Install the Obsidian Git plugin

1. In Obsidian, open **Settings** (gear icon, bottom-left)
2. Go to **Community plugins**
4. Click **Browse**
5. Search for `Obsidian Git`
6. Click the result by **Vinzent03**, then click **Install**, then **Enable**

---

### Step 5 — Install the obsidian-github-tools plugin

1. In the same **Community plugins → Browse** screen, search for `GitHub Tools`
2. Click the result by **kwhittle**, then click **Install**, then **Enable**

---

### Step 6 — Authenticate Obsidian Git with GitHub

1. In Obsidian, go to **Settings → Community plugins**, find **Git**, and click its gear icon
2. Scroll to the **Authentication/Commit Author** section
3. Enter your GitHub username in the **Username** field
4. Paste your Personal Access Token (from Step 2) in the **Password/Token** field
5. Fill in your name and email in the **Author name** and **Author email** fields (these appear on commits)

---

### Step 7 — Clone the repository into Obsidian

1. Open the **Command palette** (press `Ctrl+P` on Windows or `Cmd+P` on Mac)
2. Type `clone` and select **Obsidian Git: Clone an existing remote repo**
3. Paste the repository URL followed by `.git`  
   Example: `https://github.com/your-org/your-repo.git`  
4. When asked for a path, leave it blank and press Enter (clones into the current vault folder)

After restarting, all the repository files will appear in the left sidebar.

---

### Step 8 — Configure obsidian-github-tools

1. In Obsidian, go to **Settings → Community plugins**, find **GitHub Tools**, and click its gear icon
2. In the **Local repo path** field, enter the full path to your vault folder  
   Example: `C:\Users\yourname\Documents\my-project` (Windows) or `/Users/yourname/Documents/my-project` (Mac)  
3. In the **GitHub personal access token** field, paste your token from Step 2

---

## Editing Documents

### Step 1 — Create a new branch from main

A branch is your own private workspace. Your changes are kept separate from everyone else's work until you decide to submit them for review.

**Name your branch using your name and today's date**, so it is easy to identify who is working on what.

Format: `firstname-lastname-YYYY-MM-DD`  
Examples: `jane-smith-2026-08-19`, `alex-jones-2026-11-03`

To create the branch:

1. First, make sure you are starting from the latest version of `main`. Open the **Command palette** (`Ctrl+P` / `Cmd+P`), type `checkout`, and select **Obsidian Git: Switch to remote branch** — choose `main` from the list.
2. Open the Command palette again, type `create new branch`, and select **Obsidian Git: Create new branch**
3. Type your branch name in the format above (e.g. `jane-smith-2026-08-19`) and press Enter

The branch name now appears in the bottom status bar of Obsidian. You are ready to work.

---

### Step 2 — Write, edit, and push your changes

Use the left sidebar to navigate files. Click any `.md` file to open it.

**Switching between editing modes:**

- **Live Preview** (default): shows formatted output as you type, like a word processor
- **Source mode**: shows raw Markdown syntax

To toggle, click the book icon in the top-right corner of the editor, or open the Command palette and type `toggle live preview`.

---

**Push your changes regularly — ideally at least once a day.**

Pushing saves your work to GitHub as a cloud backup. You do not need to be finished to push — push whenever you want to save your progress.

To push:

1. Click the **source control icon** in the left ribbon (branch/arrows icon) — this opens the Source Control panel
2. You will see a list of your changed files
3. In the **Commit message** box at the top of the panel, type a brief note on what you worked on  
   Examples: `Draft section 2`, `Work in progress — FAQ page`, `End of day backup`
4. Click the **Commit-and-sync** button (cloud/upload icon at the top of the panel)

Your work is now safely backed up to GitHub on your branch.

> **Shortcut:** There is also a single Git ribbon button at the very top of the left sidebar. Hover over it to confirm the tooltip says "Commit-and-sync", then click it to push with one click using your last commit message.

---

### Step 3 — Submit your work for review

When you have finished a section and are ready for it to be reviewed, open a Pull Request (PR). A PR is a request for the maintainer to review your branch and merge it into the main documentation.

1. Make sure you have pushed all your latest changes **(Step 2)**
2. Click the **GitHub Tools** icon in the left sidebar (the GitHub logo) to open its panel
3. Click **Create PR**
4. A modal appears pre-filled with a title based on your branch name — edit the title to briefly describe what this PR contains  
   Examples: `Jane Smith — Add FAQ section`, `Alex Jones — Update installation guide`
5. Click **Create** — your browser opens to the GitHub Pull Request page, already filled in
6. *(Optional)* Add a short description in the text box explaining what you worked on and anything the reviewer should know
7. Click **Create pull request**

The maintainer will receive a notification and will review, request changes, or approve and merge your work.

Once you have submitted your PR, **do not keep editing on the same branch** — that branch is now under review.

Go back to **Step 1** and create a new branch with today's date to continue working on another section.



### What happens after your PR is submitted?

- The maintainer reviews your changes on GitHub
- If changes are requested, you will get an email notification from GitHub
- To make edits: switch back to your original branch in Obsidian (Command palette → **Switch to remote branch** → select your branch), make the changes, push, and the PR updates automatically
- Once merged, your content will be pushed to the live site



---

## Troubleshooting

**"Push rejected" or authentication error**  
Your token may have expired. Generate a new one following the token steps in Part 1 above and update it in both the Obsidian Git settings (Settings → Git → Password/Token) and the obsidian-github-tools settings.

**"Cannot push to this branch" / branch is protected**  
You are likely trying to push directly to `main`. Make sure you created a new branch in Step 1 of the workflow before making changes. Check the branch name in the bottom status bar — if it says `main`, open the Command palette and run **Obsidian Git: Create new branch** to start a fresh branch.

**I submitted a PR but want to keep editing on that same branch**  
Once a PR is open, start a new branch (Step 1) for any additional work. Do not continue adding commits to a branch that is under review — it makes the review harder to follow. The reviewer will let you know if any fixes are needed on the existing PR.

**Files I edited are not showing up in Commit-and-sync**  
Open the Command palette and run **Obsidian Git: Open source control view** to see the current status. Files in red are modified but not yet staged.

**The GitHub Tools sidebar is not visible**  
Open the Command palette and search for `GitHub Tools` to find the command to open its panel.

**I lost my branch or accidentally switched**  
Open the Command palette and run **Obsidian Git: Switch to remote branch** or **Create new branch** to get back on track. Ask the maintainer if you are unsure.
