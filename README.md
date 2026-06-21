# Al Muhaidib Group × SAP — The Autonomous Enterprise Journey

An interactive, presenter-led platform for walking Al Muhaidib Group's IT, Business, and Executive
audiences from a Group-specific use case through SAP Business Data Cloud, SAP Business AI Platform,
Joule, and the Autonomous Enterprise — ending with a live, hands-on Joule Agent workshop.

## How to open this

Keep these together in one folder:

```
index.html       ← open this in a browser — double-click it, that's it
media/           ← logos, diagrams, and all 12 demo videos
```

**`index.html` now works by simply double-clicking it** — no local server needed. All of the
page's styling and interactive logic are built directly into that one file, so the only thing
it needs alongside it is the `media` folder (kept separate because the videos are too large to
embed directly without breaking the file).

`styles.css`, `content.js`, and `app.js` are also included in this folder as readable reference
copies of what's inside `index.html`, in case you want to review or hand them to a developer —
but they are not loaded by the page itself anymore, so you don't need to keep them next to
`index.html` for it to work.

If double-clicking still doesn't play video in your specific browser setup (some locked-down
corporate machines restrict local file playback entirely), running a tiny local server is the
fallback:

```
python3 -m http.server 8080
```

then open `http://localhost:8080`.


## Navigating during the session

- **Left rail** (desktop) or **menu icon, top right** (mobile/narrow window): jump to any of the
  15 sections directly.
- **Bottom bar**: Back / Next buttons, plus a progress indicator.
- **Arrow keys**: ← and → also move between sections.
- Videos only play one at a time, and always stop and reset the moment you navigate away —
  so nothing keeps running in the background during your session.
- The **Joule bubble** (bottom right) is a lightweight, illustrative assistant — it offers
  section-relevant suggested questions and responds with a placeholder message pointing back
  to your live SAP environment. It is not a live AI connection.

## What's complete vs. what's a placeholder

| Section | Status |
|---|---|
| The Challenge (Al Muhaidib use case) | Complete |
| Your Hosts (presenter intro) | Complete — Amal Al-Rebh and Zainab Abdulsalam, with photos |
| SAP Business Data Cloud | **Placeholder** — waiting on your source material |
| How It's Built, Joule Beyond Chat, Autonomous Suite, Assistant Catalog, Finance Spotlight, What Changes, HR in Action | Complete — built from your approved SAP decks |
| Joule for Developers | **Placeholder videos** — the wheel diagram is in; the two demo videos (overview + Application Generation) are waiting on real files. See "Adding the two Joule for Developers videos" below. |
| Build Your Own Agent (Joule Studio overview) | Complete |
| → Live workshop hand-off (QR code + steps) | QR code is live. Steps are written from the workshop title only — the source PDF still wasn't shared, so it's worth checking them against the real guide before presenting |
| Joule for Consultants | Complete |
| AI Beyond Joule | Complete |
| Get Started with Joule | Complete — both real QR codes, decoded and verified |

## Recent revisions

- **Opening page rebuilt as a single-screen story.** "The Challenge" now fits on one screen
  with no scrolling, even on shorter laptop displays — a self-introduction grounded in AMG's
  real history (founded 1943), a chip-list of actual portfolio companies (SAB, Saudi National
  Bank, Arab Bank Iraq, Mansour Bank, BLOMINVEST, Seedra Ventures, Gadwa, Pioneer Properties),
  an investment-specific AI insight, and the SAP Business Data Cloud → SAP Business AI
  Platform → Joule flow, all visible together.

## Adding the two Joule for Developers videos

These two video files couldn't be uploaded through any available channel (project upload,
zip, and chat attachment all rejected `.mp4`/archives), so the page currently ships with two
clearly-labeled placeholder slots instead of broken video players. To add them yourself once
you have the files in hand:

1. Rename your two source files to match what the code expects:
   - `joule-for-developers-overview.mp4`
   - `joule-application-generation-demo.mp4`
2. Drop both into `media/video/`, alongside the other 12 videos already there.
3. In `content.js` (and the matching block inside `index.html`), search for
   `pending upload` and replace the two placeholder `<div class="video-frame video-frame--pending">`
   blocks with real `<video>` markup — copy the exact pattern used by any other working video
   on the page (e.g. search for `v-hr-agent` for a working example to mirror).

No other file needs to change, and nothing else on the platform depends on this — every other
video, the modal pop-up player, navigation, and all 15 sections work today regardless of whether
these two are filled in.



Each placeholder section is clearly marked in the platform itself with an amber banner, so it
won't be mistaken for finished content if presented as-is.

## Filling in what's left

Send me:
1. Your SAP Business Data Cloud slides/content
2. The workshop PDF ("Create Joule Agents and Skills for SAP SuccessFactors with SAP Build")
3. A working link (WeTransfer or similar) to the two Joule for Developers videos, if you'd
   rather I wire them in than do it yourself per the steps above

and I'll drop them into the existing structure in place — no rebuild of the rest of the platform
needed.

## A note on one slide

One slide from `SAP_Autonomous-AMG.pptx` (the "Autonomously Orchestrated Finance" snapshot,
slide 12) was marked **INTERNAL – SAP Only** in the source file and has been deliberately left
out of this customer-facing platform.

## Content sourcing

All text, diagrams, screenshots, and videos are used as-is from your six approved SAP decks:
`SAP_Autonomous-AMG.pptx`, `AMG2.pptx`, `J4C.pptx`, `Joule_Agents.pptx`, `AI_Beyond_Joule.pptx`,
and `Get_started_with_Joule_today.pptx`. Videos are the original files at full resolution with no
re-encoding. Dense architecture/process diagrams are embedded as high-resolution images (for
exact fidelity to the approved SAP artwork) inside an otherwise fully interactive HTML
experience — navigation, tabs, video playback, and the Joule widget are all real, built
components, not images.
