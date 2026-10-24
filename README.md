# Ergon

Ergon is the showcase part of Taejae University's learning suite. Work lives in **studios**; a **showroom** puts it on show for a given audience and time; inside a showroom, each **booth** holds a team's (or a lecturer's) **pieces**: videos, slide decks, demos.

This repository holds the faculty web app as a single page, `index.html`.

## What is in it

- **Home** (after sign-in): a carousel of live and coming showrooms, then the showrooms and studios. Everyone has a private studio of their own; a course's team studios show to that course's host.
- **Top menu**: About, Showrooms, Studios, Settings (profile, change password, sign out).
- **Invite** (host, on a showroom): choose who can open it (Public: anyone with the link, no sign-in · Taejae: anyone at Taejae after sign-in · Class: the course's class after sign-in), then copy the link or download its QR code and a printable invitation card. A Taejae or Class link shows visitors a gate that asks them to sign in; there is no standing sign-in link on visitor pages. The gate uses the same sign-in as faculty: a Taejae email and password on the shared Supabase project (the account used for Telos). In this version the audience is checked in the page; the class list is not connected yet.
- **Showroom › Booth › Piece**: one page template at every level. A poster in the showroom's colour with a stage that cycles through the pieces, tiles of what is inside, and the facts. A piece has nothing below it, so its poster folds into a thin band and the piece plays across the full width (Google Drive player for videos, Google Slides viewer for decks).
- **Showrooms in this version**
  - 뇌과학 아카데미 특강 (Oct 26 – Nov 6, 2026): Prof. Kwahk's Data Science & AI lectures for high-school students. Two booths (Week 1, Week 2), real videos and Google Slides. Public: opens without sign-in.
  - DA321 Project Demo and Presentation: sessions and team booths; team work is not connected yet.
  - AIRshow: coming soon.

## Roles

Faculty and students get the same Ergon after sign-in (About, Showrooms, Studios, Settings). What they can do comes from their role in each showroom: **host** (runs it; the only one who sees Invite), **exhibitor** (sends work from their studio to their own booth) or **visitor** (views). Each showroom lists its hosts and exhibitors as SHA-256 hashes of their sign-in email, so no address is written in the page. Like the audience, roles are checked in the page in this version.

## Sign-in

Same as Telos and TaeSylla: a Taejae email (`@taejae.ac.kr`) and password against the shared Supabase project. For faculty the name comes from `faculty_profiles`; a first sign-in with `must_change_password` asks for a new password. The session is kept in `sessionStorage`, so a refresh keeps you signed in and closing the tab signs you out. A public showroom link (for example `#s/brain`) opens without sign-in and shows only that showroom.

## Pages

`#about`, `#home` (Showrooms), `#studios`, `#settings`, `#s/<showroom>`, `#b/<booth>`, `#p/<piece>` — for example `#s/brain`, `#b/brain-w1`, `#p/w1v2`.

## Running it

Open `index.html` in a browser, or serve the folder with any static host. For visitors to see the lectures, the Drive files must be shared as "Anyone with the link · Viewer". It is published with GitHub Pages at https://jkwahk02.github.io/Ergon/ (the academy showroom: https://jkwahk02.github.io/Ergon/#s/brain).
