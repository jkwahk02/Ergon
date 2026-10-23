# Ergon

Ergon is the showcase part of Taejae University's learning suite. Work lives in **studios**; a **showroom** puts it on show for a given audience and time; inside a showroom, each **booth** holds a team's (or a lecturer's) **pieces**: videos, slide decks, demos.

This repository holds the faculty web app as a single page, `index.html`.

## What is in it

- **Home** (faculty, after sign-in): a carousel of live and coming showrooms, then every showroom and the studios grouped by course.
- **Showroom › Booth › Piece**: one page template at every level. A poster in the showroom's colour with a stage that cycles through the pieces, tiles of what is inside, and the facts. A piece has nothing below it, so its poster folds into a thin band and the piece plays across the full width (Google Drive player for videos, Google Slides viewer for decks).
- **Showrooms in this version**
  - 뇌과학 아카데미 특강 (Oct 26 – Nov 6, 2026): Prof. Kwahk's Data Science & AI lectures for high-school students. Two booths (Week 1, Week 2), real videos and Google Slides. Public: opens without sign-in.
  - DA321 Project Demo and Presentation: sessions and team booths; team work is not connected yet.
  - AIRshow: coming soon.

## Sign-in

Same as Telos and TaeSylla: a Taejae faculty email (`@taejae.ac.kr`) and password against the shared Supabase project. The name comes from `faculty_profiles`; a first sign-in with `must_change_password` asks for a new password. The session is kept in `sessionStorage`, so a refresh keeps you signed in and closing the tab signs you out. A public showroom link (for example `#s/brain`) opens without sign-in and shows only that showroom.

## Pages

`#home`, `#studios`, `#s/<showroom>`, `#b/<booth>`, `#p/<piece>` — for example `#s/brain`, `#b/brain-w1`, `#p/w1v2`.

## Running it

Open `index.html` in a browser, or serve the folder with any static host. For visitors to see the lectures, the Drive files must be shared as "Anyone with the link · Viewer". The repository is private for now; switch it to public and turn on GitHub Pages when the academy opens.
