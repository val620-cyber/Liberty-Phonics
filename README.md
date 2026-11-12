# Liberty Phonics

An English phonics app for Spanish speakers. Students learn the sounds of English one phonogram at a time, practice a little every day, and earn stars as they go.

("Liberty Phonics" is a placeholder name. Change it any time.)

## What works today (World 1)

- 7 levels teaching the alphabet A to Z, four letters at a time, with every sound each letter makes
- Sound-first cards: tap a sound to hear only that sound; tap the example word beside it to hear the word
- A vowel drill at the end of every level quiz
- Sound Board: tap any letter to hear its sounds
- Daily practice checklist: phonogram cards, Hear & Tap, and Build a Word (tap or drag letters onto the lines)
- A bonus match game
- White star for passing a level, gold star for a perfect score
- Day streak and a calendar that shows every day practiced
- English / Spanish switch, with a pronunciation tip for Spanish speakers on every letter
- Teacher Studio for recording the sounds in your own voice
- Button vibration and sound effects
- A moving background with drifting stars, and a Freeze button that stops the motion for anyone who needs calm

Progress is saved on each person's own phone or computer. There are no accounts and nothing to pay for.

## Put it online for free (GitHub Pages)

A "repository" is a project folder that lives on GitHub. "GitHub Pages" turns that folder into a website at no cost.

1. Sign in at github.com and press the **+** at the top right, then **New repository**.
2. Name it `liberty-phonics`, choose **Public**, and press **Create repository**.
3. Press **uploading an existing file**, add `index.html`, `README.md` and `CLAUDE.md`, then press **Commit changes**.
4. Open **Settings**, then **Pages**. Under "Branch" choose **main** and press **Save**.
5. Wait about a minute. Your app will be live at `https://YOUR-USERNAME.github.io/liberty-phonics/`.

Send that link to your family. On an iPhone, open it in Safari, press the Share button, and choose **Add to Home Screen** so it opens like an app.

## Record your voice

Open the app from its web address, press the gear, then **Teacher Studio**, and enter the teacher code: **1776**. Your device remembers it until you press Lock.

Teacher Studio has three lists. For each row, press ⏺, speak, and press ⏹. Press ▶ to check it.

1. **Phonogram sounds (39):** say only the sound. These are what students hear when they tap a sound.
2. **Example words (39):** say only the word, such as "apple." Students hear it when they tap the example bubble.
3. **Build-a-Word words (43):** say only the word, such as "cab." Students hear it in the word-building game.

The word lists are optional. Until you record a word, a computer voice says it.

To share your recordings with every student:

1. Press **Download recordings (zip)** at the bottom of Teacher Studio.
2. Double-click `audio.zip` on your computer. A folder named `audio` appears.
3. On your GitHub repository page, click **Add file**, then **Upload files**, drag the whole `audio` folder in, and press **Commit changes**.

Or give the zip to Claude Code and say: "Unzip this into the `audio` folder and push it."

## Working on it with Claude Code

Open this repository in Claude Code and tell it what you want in plain words. `CLAUDE.md` already explains the vision, the design rules, and the roadmap, so Claude Code reads that first.

Good first requests:

- "Add World 2 with the vowel teams and consonant teams."
- "Make the calendar show which letters to practice on each upcoming day."
- "Add student profiles so my whole family can share one tablet."

## Good to know

- **The teacher code is a light lock.** It keeps students out of Teacher Studio, but because the project is public on GitHub, a determined person could find it. To change it, ask Claude Code: "Change the teacher code to ____."
- **Vibration** works on Android phones. On iPhones it only works on recent versions of iOS, and Apple may change that.
- **Clearing browser data** on a device erases that device's progress.
- **Please check my teaching content.** The sounds, keywords, and Spanish tips are a starting draft. You are the teacher, so correct anything that does not match how you teach it.
