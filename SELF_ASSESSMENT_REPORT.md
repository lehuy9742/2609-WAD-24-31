# Self-assessment — PA#1 (Idea and wireframe)

Submitted by:

- 24120048 — Lê Hoàng Hiếu
- 24120061 — Lê Nguyễn Gia Huy
- 24120131 — Nguyễn Anh Sang

Total we claim: **100 / 100**

| Criterion | Max | We claim | Evidence |
| --- | --- | --- | --- |
| 1. The problem and the users | 20 | 20 | `PROPOSAL.md` / `PROPOSAL-en.md` §2: the problem fits in one paragraph a stranger understands, without "platform" or "ecosystem". §3: two user types, each with the job they want done. |
| 2. Scope, with a *Not building* list | 15 | 15 | §5: a *Building* list split into a core part that alone runs the main flow and a personal part built after it, with named data sources (a `robots.txt`-respecting crawler starting with ITviec and TopDev, plus hand entry from company career pages). 11 concrete **Not building** items (no employer accounts, no admin interface, no CV upload, no email/SMS notifications, no mobile app, no bulk scraping…). |
| 3. Three screens of the main flow | 35 | 35 | `wireframes/01`, `02`, `03` follow the main flow in order (search → results → details and source check) and are readable at the submitted size. They share one scenario: the filters chosen on Screen 1 appear on Screen 2, and its first result is the posting on Screen 3. Every button and link on them leads to the next screen or to a page §6 names. |
| 4. Each screen explained | 15 | 15 | §6: one paragraph per screen saying what the student is doing there and where every button or link takes them, linked to its image file. A shared list covers the top bar, footer, sample-data strip and status labels, and explains where the drawing differs from the real site (top-bar highlight, pre-selected chips). |
| 5. `AI-LOG.md` | 15 | 15 | `AI-LOG.md`: four entries in the course template format (2026-10-15 Claude chat for the initial idea; three 2026-10-17 Claude Code entries for the proposal, the scope and this report), each with the tool and what we asked for, plus what we kept, rejected or did by hand — for example rejecting LinkedIn scraping because of its terms, and rejecting the redraw of the wireframes. |
| **Total** | **100** | **100** | |

## What we did not manage

Our mockups ended up with more than our first scope: saving jobs, student accounts, notifications, reporting suspicious postings and a profile panel. Instead of redrawing the screens, we added these to the Scope as a separate "personal" part, built only after the core main flow works, and fenced them with *Not building* items (no CV upload, no email/SMS, no social login, no admin interface).

The drawings also have small differences from the real site that §6 explains instead of redrawing: "Trang chủ" is highlighted in the top bar on all three screens, and the pages reached from them (saved jobs, profile, safety guide, the report box) are described in text, not drawn.

## What we would do differently

Agree on the Scope's *Building* list and one sample scenario before anyone draws, so the wireframes use the same data from screen to screen and every button already has a place in the proposal. Then check every button in the drawings against the Screens section before polishing them.
