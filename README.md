# happiestt anniversaryy gugluu (month 18)

A chat app that looks like Claude, except the assistant is gullaa and every chat in the sidebar is one of our months. The 18th is locked until she has opened all the others.

## Deploy (GitHub Pages)
This folder is already a git repo, with everything committed on `main` and `origin` set to github.com/yuguuvermaa/eighteen.
1. On GitHub, create a new public repo named `eighteen`. Leave it empty: no README, no .gitignore, no licence.
2. In Terminal, in this folder, run `git push -u origin main`.
3. In the repo, go to Settings, Pages, Deploy from branch, main, / (root). Wait a minute, then open https://yuguuvermaa.github.io/eighteen/

After you change anything: `git add -A && git commit -m "what changed" && git push`. Pages updates in about a minute.

The WhatsApp preview image points to yuguuvermaa.github.io/eighteen/photos/og.jpg (a small copy of the 31 may 2026 photo). If you pick another repo name or photo, change the `og:image` line near the top of index.html, and the remote with `git remote set-url origin <new url>`.

## Edit words
Everything she reads or hears is set at the bottom of index.html, in four blocks:
- `MONTHS`: one entry per month. Title, her question, photos, the hidden "thought", and the story. A story can mix paragraphs, photos in the middle, and shayaris (examples are in the comment right above it).
- `EIGHTEEN`: the locked 18th chat and the letter that opens from it.
- `SONGS`: which song plays where, and `from`, the second it starts at (and loops back to) so it can skip a slow intro.
- `SITE`: the greeting, the tutorial, gullaa's canned replies when she types, the menu jokes.

## Songs
They're in `songs/` with exactly these names. All six were levelled to the same loudness, so no song jumps out louder than the others. They were re-encoded as 192 kbps mp3 so the start second lands exactly. If you swap one, keep it an mp3 with the same name. Downloads from Spotify, Apple Music or JioSaavn won't work, because they only play inside those apps.

| file | song | plays during | starts at |
|---|---|---|---|
| `home.mp3` | tum se hi | the greeting | 0:57.5, just before the first "tum se hi" chorus |
| `1-3.mp3` | jo tum mere ho | months 1 to 3 | 0:36, just before the first full chorus |
| `4-8.mp3` | raataan lambiyan | months 4 to 8 | 0:45.5, the build-up into "raataan lambiyan" |
| `9-12.mp3` | tera hone laga hoon | months 9 to 12 | 0:28.5, just before Atif comes in, leading to the title |
| `13-17.mp3` | janam janam | months 13 to 17 | 0:21, just before the opening "janam janam" line |
| `18.mp3` | mann mera 2.0 | the 18th and the letter | 0:42.5, just before the first chorus |

Each song starts about 2.5 seconds before its line, so the line lands just as the fade-in finishes, and loops back to the same spot when it ends. To move a start point, change `from` (in seconds) for that song in `SONGS`.

Music starts on her first tap. When she opens a chat from a new stretch, the old song fades out as the new one fades in, and a small "now playing" label shows for a few seconds. Moving between months in the same stretch doesn't interrupt it. The locked 18th keeps the current song, so mann mera 2.0 only plays once it's unlocked. If a file is missing, whatever was playing keeps playing.

Photos go in `photos/`, named by month (`04-8sep-a.jpg` is month 4). Names are case sensitive on GitHub Pages. Short clips work too (`01-26may.mp4`): they loop silently like a live photo, with a `.jpg` of the same name as the still.

## What she'll experience
1. The gullaa spark spins in, then "happiestt anniversaryy gugluu" writes itself out, with a live "together" counter under it.
2. A one-time popup: every chat on the left is one of our months, start from the 1st. On her phone it spotlights the ☰ button. Her tap on "show me" also starts the music.
3. Each chat plays like a real Claude conversation: her message with that month's photos, gullaa "thinking about you…", a collapsible "Thought for 31 days", then the story streams in. Tap a photo to see it full size. The second time she opens a chat it shows instantly.
4. Under each reply: copy, 👍 (hearts), 👎 ("feedback not accepted"), retry ("same answer. it's always you").
5. The 18th sits starred at the top with a lock. Opening it early shows a fake usage-limit card with a progress bar ("you've read 12. 5 to go."). Once all the others are open it unlocks with a toast, and the letter opens in a side panel (full screen on the phone) with a countdown to month nineteen.
6. She can type in the box. gullaa answers from canned replies ("have you eaten?" and so on), with a cute fallback for anything else.
7. Little things: the model picker (Gullaa 17 retired, Gullaa Forever still training), the "Forever plan" profile menu, "gullaa can make mistakes. loving you isn't one of them."

Easter egg: between 01:20 and 01:29 am IST a line appears under the greeting. On the 25th it says "eighteen months ago, right now."

## Testing
- `?unlock` at the end of the url opens the 18th without reading everything.
- `?reset` forgets what's been read and brings the tutorial back.
- Open it once yourself before sending, then use `?reset` so her copy starts fresh. Reading state is saved per browser, so your phone and hers are separate anyway.
