# Liberty Phonics — project brief for Claude Code

## Who this is for

Val is the owner and teacher. She is new to coding: explain every step in plain language, define jargon, and do the technical work yourself (commits, pushes, file moves). The students are her Spanish-speaking family and friends and, later, her paying English students. Many are adults; many are on phones.

## What the app is

A phonics-first English course. Students learn every sound of every phonogram, then spelling rules, then build and read words. The teaching approach follows the Orton-Gillingham / Spalding tradition that Val knows through *Spell to Write and Read* (SWR).

**Copyright rule:** phonograms and spelling rules are facts and may be taught. Never copy SWR's (or any curriculum's) wording, word lists, rule phrasing, markings, or artwork. Write everything in our own words.

## How Val teaches (follow this order of ideas)

- **Alphabet first, A to Z.** Levels unlock the letters in alphabet order, four at a time.
- **The sound is the star.** A phonogram card plays only the pure sound when tapped ("a says ă, ā, ah"). Example words are small and off to the side, never the focus.
- **Vowels get extra drilling.** Every level quiz ends with a vowel drill ("Which sound of a did you hear?"). Keep adding vowel practice wherever it fits.
- **Build before you read.** Beginners build small words from sounds they know (the Build-a-Word game: picture on top, lines in the middle, letter spheres below; tap or drag; a correct line turns gold, a wrong one flashes red). Words grow longer as letters unlock. Only use letters already learned, each saying its first sound (the `WORDS` list).
- **Reading-style games come later.** Fill-in-the-missing-letter and anything that shows whole words belongs after the alphabet is finished. Today a missing-letter hint appears in Hear & Tap only for sounds that have no teacher recording yet; it disappears as recordings are added.
- **Right after the alphabet: letter teams** (World 2 below).

## Hard constraints

- **Cost: $0.** Static files on GitHub Pages. No paid services, no server, no build step unless Val approves it.
- **Simple to maintain.** Today the whole app is `index.html` (vanilla HTML/CSS/JS). Split into files only when it clearly helps, and keep it runnable by opening the page.
- **Works offline-first on phones.** Progress lives in `localStorage` (key `liberty-phonics-v1`). Wrap storage in try/catch.
- **Bilingual.** Every student-facing string exists in English and Spanish (the `T` object). Never add a string in one language only.

## Design rules (Val is very sensitive to these)

- Soft, round, puffy, 3D. Spheres and pills. **No sharp corners or flat squares anywhere.**
- Bouncy, Apple-like motion. Reuse the `.puff` (pill button) and `.orb` (sphere) classes.
- Palette: red `#D7263D`, navy `#16295C`, baby blue `#9BD3F7`, white, and gold `#F7B801`. These are the theme of the whole app: they stand for the USA and freedom, so every screen should carry them.
  - Layer them creatively: navy night-sky panels with small stars, stacked red / white / baby-blue ledges under panels, and spheres that alternate red, white, navy and baby blue.
  - Val loves contrast. Use lighter and darker shades of these same colors (never new hues) to create depth, optical illusions and a feeling of space: concentric rings, stacked ledges, large soft circles in the background.
  - Gold stays special: stars and rewards first, plus tiny accents.
- **Living background on every screen** (`#sky` and `#stars`): slow lava-lamp color blobs, shiny floating spheres down the sides on wide screens, and small stars that drift and bounce off the 3D spheres. The stars stay **behind** the cards and panels and never float over them (Val finds that distracting). Lively but subtle. No plain empty areas, on phones or on computers.
- **Freeze / Bounce button** (`#calm`, always visible): Freeze halts all ambient motion and confetti so an overstimulated student can focus; Bounce resumes it. Any new ambient animation must stop when `html.frozen` is set (`S.calm`).
- Sound cards: each sound is a free-floating sphere joined by a line to its example bubble. Keep example text large and easy to read.
- Font: Arial Rounded where available, Arial otherwise. Phonogram cards are lowercase.
- Every tap gives feedback: `buzz()` for vibration and `sfx` for sound.
- Reward small wins like a video game: stars, confetti (`celebrate()`), checkmarks. Daily consistency is the thing to celebrate most.
- Patriotic and Christian tone. "In God We Trust" stays in the header.

## How the code is organized (`index.html`)

1. **Content** — `P` (phonograms, sounds, keywords, Spanish tips), `LV` (which phonograms unlock per level), `WORDS` (Build-a-Word lists per level), `T` (translations)
2. **Saved progress** — `S` = `{lang, done, days, sfx, calm, teacher}`
3. **Audio** — `play(id)` uses, in order: a recording on this device (IndexedDB), a file listed in `audio/manifest.json`, then a computer voice reading the keyword
4. **Screens** — `SCREENS` object; each function returns HTML for one screen
5. **Actions** — `ACT` object; buttons call these through `data-a` attributes
6. **Living background** — the `fx…` functions draw the drifting stars on a canvas

Sound ids are the phonogram plus a number: `a1`, `a2`, `a3`, `qu1`.

### Teacher recordings

Teacher Studio is hidden behind a teacher code (`TEACHER_CODE` in `index.html`). It is a light lock to keep students out, not real security: the repository is public, so the code can be read there. Nothing a student records can reach other students.

Teacher Studio exports `audio.zip` containing files such as `a1.m4a` plus `manifest.json`. Unzip its contents into `/audio/` at the repository root and push. When Val hands you a zip, do this for her.

## Roadmap

1. **Polish World 1:** a "My turn" button on each sound card (student hears the teacher, records themselves, plays both back; never replaces the teacher's recording), installable PWA (manifest, icons, service worker for offline), student profiles for shared devices, calendar that shows which letters are planned for each day, export/import of progress.
2. **World 2 — Vowel & Consonant Teams (the very next thing after the alphabet).** Most common first, a few per level, every sound of each team, same sound-first cards, vowel-team drills, and Build-a-Word with team tiles (a team such as `sh` is one tile):
   - Vowel teams: ee, ea, ai, ay, oa, ow, ou, oo, oi, oy, au, aw, ew, igh, ie, ey.
   - Consonant teams: sh, ch, th, wh, ck, ng, ph, kn, wr, tch, dge.
   - Vowel-consonant teams: ar, er, ir, or, ur.
   - Sound ids follow the same pattern (`sh1`, `ow1`, `ow2`), so Teacher Studio picks them up automatically once they are added to `P`.
3. **World 3 — Rules:** spelling rules in our own words (silent final e jobs, c and g softening, vowels at the end of a syllable, etc.), each with a mini game.
4. **World 4 — Word Building:** blend phonograms into words; dictation with the teacher's voice.
5. **World 5 — Reading:** short passages with teacher-recorded audio:
   - Scripture. Val prefers the Legacy Standard Bible; NASB, ESV, NKJV and KJV are also fine with her. All but the KJV are copyrighted, so **confirm the publisher's permission policy and add the required credit line before adding any verse.** The KJV is public domain in the United States and is the safe default until permission is confirmed.
   - The Ten Commandments and gospel-centered verses.
   - American civics and mottos ("In God We Trust").
   - Short paragraphs explaining how free markets and capitalism work.
6. **Later, when there is budget:** accounts and a teacher dashboard (a free tier such as Supabase), so Val can see each student's progress.

## Before you finish any change

- Test at phone width (390px) in both languages.
- Complete a level and all three daily tasks without console errors.
- Confirm nothing has square corners.
