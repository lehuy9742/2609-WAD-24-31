# AI-LOG — PA#1

## 2026-10-15 — initial project idea
Tool: Claude (claude.ai chat).  
Asked for: ideas for a site that helps students find part-time jobs and internships without searching many job sites one by one.  
Kept: respecting each website's `robots.txt` when collecting job postings. It became the data-source line in `PROPOSAL.md` §5 and the **No bulk scraping** item: we only take data a source allows, and never bypass logins, CAPTCHAs or rate limits.  
Rejected: crawling LinkedIn for job postings. LinkedIn's terms of service forbid scraping, so we did not build the project on a source we are not allowed to use.  

## 2026-10-17 — reformat the proposal and check the wireframes
Tool: Claude Code.  
Asked for: read the PA#1 rubric, reformat `PROPOSAL.md`, and check the three wireframes against it.  
Kept: the reformatting (no italics or empty "Role" column in the Team table, the screen named on each Main flow step, a link to each wireframe file in §6). Also kept the text changes it made so the proposal matches the drawings: the filters actually drawn are job type / location / pay / experience (no "working schedule" filter), the Screen 3 button is "Ứng tuyển tại nguồn" (Apply at source) rather than "Mở tin tuyển dụng gốc" (Open original posting), and the Screen 2 cards show posting date and verification status rather than the source name.  
By hand: it pointed out that one student ID had 9 digits; we corrected it ourselves.  

## 2026-10-17 — align the scope with the wireframes
Tool: Claude Code.  
Asked for: make the proposal explain every button the wireframes show.  
Kept: the features it added to §5 in a limited form (email/password student accounts, saved jobs, a short profile without CV upload, in-site notifications, reports that never label a posting by themselves, static pages), the new *Not building* items (no CV upload, no email/SMS notifications, no Google/Facebook login), and the §6 text describing every button and the shared top bar.  
Rejected: its first suggestion, which was to remove the save-job buttons, account menu, notification bell, report link and CV panel from the wireframes. Redrawing all three screens a day before the deadline was too risky, so we widened the scope instead.  

## 2026-10-17 — self-assessment and English version
Tool: Claude Code.  
Asked for: a draft of `SELF_ASSESSMENT_REPORT.md`, and an English version of the proposal and reports.  
Kept: the table layout and evidence lines, the *What we did not manage* section, and `PROPOSAL-en.md` as an English translation of `PROPOSAL.md`.  
