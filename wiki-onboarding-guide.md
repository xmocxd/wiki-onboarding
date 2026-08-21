# Wiki Onboarding Guide

This guide outlines 2 different methods to edit documents on the wiki.  These documents are simple markdown files hosted on GitHub that get converted into web pages visible on the live wiki.  To get started quickly, editing online directly on GitHub (method 1) is the absolute simplest way to edit the markdown files, but installing a local editor provides a more powerful ediitng experience for doing a large amount of writing work.

## What is Markdown?

Markdown is a lightweight way to format text using plain characters. Instead of clicking a "Bold" button, you type `**bold**`. Instead of inserting a heading from a menu, you type `# My Heading`.

Markdown files end in `.md` and look like plain text when opened in any editor, but render as formatted documents in Obsidian, GitHub, and most documentation sites.

A quick reference:

```markdown
# Heading 1
## Heading 2

**bold text**
*italic text*

- bullet item
- another item

[link text](https://example.com)

![image alt text](path/to/image.png)
```

# Method 1 - Edit Online via GitHub (Basic)

This method is the quickest way to start editing, requiring only a GitHub account and no other setup.  **The main limitation of this method is that you are unable to see the formatted document while editing**, working by editing the text-based code in the markdown file, then switching to a different mode to preview the formatting.


## Editing Documents

To any text on the wiki:

1. **Go to `https://github.com/xmocxd/wiki-onboarding/`** (TO ADD REAL URL)
2. Make sure you are editing on the **MAIN** branch.
   1. This should be the default branch when opening the repository URL, ---- the current branch is also shown at the top of the editor.
3. Browse and find the `.md` file you want to edit from the list, click on the file
4. Use **Edit** and **Preview** buttons to switch between editing the Markdown and viewing the formatted result.
   - Note: Markdown shortcuts such as `Ctrl+B` for bold text still work within GitHub’s Markdown editor.  *(See below for full list)*
5. When finished, click **Commit changes...** (or press `Ctrl+S`).
6. Select **Create a new branch for this commit and start a pull request**.
7. Enter any branch name you want, or use your name and date. You can optionally add a description.
8. Click **Create pull request** to submit the changes.



GitHub Markdown Editor Hotkeys
------------------------------

```
--- Text Styling ---
Bold:
  Windows/Linux: Ctrl + B
  Mac:           Cmd + B
Italic:
  Windows/Linux: Ctrl + I
  Mac:           Cmd + I
Inline Code:
  Windows/Linux: Ctrl + E
  Mac:           Cmd + E
Link:
  Windows/Linux: Ctrl + K
  Mac:           Cmd + K

--- Lists & Quotes ---
Ordered List:
  Windows/Linux: Ctrl + Shift + 7
  Mac:           Cmd + Shift + 7
Unordered List:
  Windows/Linux: Ctrl + Shift + 8
  Mac:           Cmd + Shift + 8
Blockquote:
  Windows/Linux: Ctrl + Shift + .
  Mac:           Cmd + Shift + .

--- Workflow & Editor ---
Toggle Write/Preview:
  Windows/Linux: Ctrl + Shift + P
  Mac:           Cmd + Shift + P
```



# Method 2 - Edit Locally with Obsidian (Advanced)

This method requires a more involved setup, but allows you to edit the files like a word processor, **where you can see and edit the formatted document live without having to switch between code and preview.**



## Initial Setup

### Step 1 — Prerequisites: Git must be installed on your computer

Obsidian Git relies on the system Git binary to operate. Check whether Git is already installed before continuing.

**Mac:** 
Git is usually pre-installed. Open **Terminal** (press `Cmd+Space`, type `Terminal`, press Enter) and run:

```bash
git --version
```
If you see a version number (e.g. `git version 2.39.0`), you are ready. If you see an error or a prompt to install Xcode Command Line Tools, click **Install** and wait for it to finish.

**Windows:** 
Git is usually not installed by default.

1. Download the installer from https://git-scm.com/install/windows
2. You can **USE ALL DEFAULT OPTIONS** on the installer, just click through all with Next

 After installing, you do not need to open Git again — Obsidian will use it automatically.

### Post-install setup for Git

After git is installed, **open a terminal / command line window and run the following commands** (entering in an actual name and email):

```bash
git config --global user.name "your name"
git config --global user.email "your-email@whatever.com"
git config --global push.default upstream
```



---

### Step 2 — Create a GitHub Account & Get Personal Access Token

**First, create an account on GitHub** if you don't already have one.

**Next, create a Personal Access Token.**  This will be used by the editor plugin to authenticate.

1. Go to [github.com/settings/tokens](https://github.com/settings/tokens)
2. Click **Generate new token → Generate new token (classic)**
3. Under **Select scopes**, check the box next to **repo** (this covers all permissions needed)
4. Add a note (required) -- can be anything
5. Select NO EXPIRATION or the maximum allowed expiration
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
3. IF FIRST TIME RUN:
   1. Under **Restricted Mode**, click **"Turn off and Reload"**
   2. After reloading you should be able to use community plugins
4. (Via the same page) Click **Browse**
5. Search for `Git`
6. Click **Git** by **Vinzent**, then click **Install**, then **Enable**

---

### Step 5 — Clone the Wiki repository

1. Open the **Command palette** (press `Ctrl+P` on Windows or `Cmd+P` on Mac)
2. Type `clone` and select **Obsidian Git: Clone an existing remote repo**
3. **Paste the following URL** -- `https://github.com/your-org/your-repo.git` (TODO: ADD REAL URL)
4. **When asked for a path, leave it blank** and press Enter (clones into the current vault folder)
5. **Leave "depth" question blank**

After restarting, all the repository files will appear in the left sidebar. -- **(CLICK FOLDER ON LEFT SIDEBAR TO SEE THE FILES IF YOU DONT SEE ANYTHING)**

---

After finishing the intial setup, you should be able to edit documents using the next steps.   You should not have to modify any of these settings again unless you need to install this on a new machine.





## Editing Documents


### Step 1 — Create a new branch from main

A branch is your own private workspace. Your changes are kept separate from everyone else's work until you decide to submit them for review.

To create the branch:

1. First, make sure you are starting from the latest version of `main`. Open the **Command palette** (`Ctrl+P` / `Cmd+P`), type `switch`, and select **Obsidian Git: Switch to remote branch**
   1. Select `origin`
   2. Select `origin/main` from the list.
2. Open the Command palette again, type `create new branch`, and select **Obsidian Git: Create new branch**
3. Type a unique branch name **(Can be anything unique, but can just use your name + date -- e.g. `jane-smith-2026-08-19`)** and press Enter
   1. **NOTE -- IT WILL NOT SAY ANYTHING, JUST TYPE THE NAME AFTER SELECTING THE COMMAND**

**The branch name now appears in the bottom status bar** of Obsidian. You are ready to work.

---

### Step 2 — Write, edit, and push your changes

Use the left sidebar to navigate files. Click any `.md` file to open it.

**Switching between editing modes:**

- **Live Preview** (default): shows formatted output as you type, like a word processor
- **Source mode**: shows raw Markdown syntax

To toggle, click the THREE DOTS next to the book icon in the top-right corner of the editor, and click SOURCE MODE



**After making some edits, push the changes online to GitHub:**

- Push your changes regularly — ideally at least once a day.
- Pushing saves your work to GitHub as a cloud backup. You do not need to be finished to push — push whenever you want to save your progress.

To push:

1. Click the **source control icon** in the left ribbon (branch/arrows icon) — this opens the Source Control panel --- **GIT SOURCE CONTROL ON FAR LEFT VERTICAL MENU** (TOWARD BOTTOM)
2. **OPENS A BAR ON THE RIGHT SIDE WITH OPTIONS**
3. Click the **Commit-and-sync** button (cloud/upload icon at the top of the panel) -- **CLICK THE CIRCLE UP ARROW FOR COMMIT AND SYNC**
4. If prompted, type the name of your branch again in the text box that comes up talking about remote branch name -- (It should prompt you only 1 time each time you create a new branch)
5. **ON FIRST TIME RUN, it will prompt you to authenticate with GitHub**
   1. **Click Sign In**
   2. **Click Use Token**
   3. **Paste in your Personal Access Token**



---

### Step 3 — Submit your work for review

When you have finished a section and are ready for it to be reviewed, open a Pull Request (PR). A PR is a request for the maintainer to review your branch and merge it into the main documentation.

1. Make sure you have pushed all your latest changes **(Step 2)**
2. **Go to `https://github.com/xmocxd/wiki-onboarding/compare/(your branch name)`**, ---- also if you just go to the main repo page, you should see a banner prompting you to create a pull request
3. Click **Create pull request**
4. *(Optional)* Add a short description in the text box explaining what you worked on and anything the reviewer should know
5. Click **Create pull request** again on this page



### --- REPEAT STEPS 1-3 as needed to edit ---

- Once you have submitted your PR, **do not keep editing on the same branch** — that branch is now under review.
- **Go back to Step 1** and create a new branch to continue working on another section.



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
