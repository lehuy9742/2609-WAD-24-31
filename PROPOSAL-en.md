# PROPOSAL — CampusJob Trust

*English version of [`PROPOSAL.md`](PROPOSAL.md). The wireframes are in Vietnamese, so on-screen labels are quoted in Vietnamese with an English gloss.*

## 1. Team

| #   | Full name         | Student ID |
| --- | ----------------- | ---------- |
| 1   | Lê Hoàng Hiếu     | 24120048   |
| 2   | Lê Nguyễn Gia Huy | 24120061   |
| 3   | Nguyễn Anh Sang   | 24120131   |

## 2. The problem

Students looking for a part-time job or an internship usually have to open many different websites to find postings. Some postings are duplicated, some expired long ago, and many leave out exactly what a student needs to know: the working schedule, the experience required, or a link to apply. Students spend a lot of time reading posting after posting and still cannot tell where a posting came from or whether it is still open. CampusJob Trust collects postings in one place so students can filter them by what they need, see which source each posting came from and when it was last checked, and then decide for themselves whether to open the original posting and apply. The site does not declare any posting safe or fraudulent; it only shows what is known and what the source did not provide.

## 3. Users

| User type | Who they are | What they are trying to get done |
| --- | --- | --- |
| **Primary** | University students looking for a part-time job or an internship | Quickly filter postings that fit their class schedule and experience, see the source and when it was last checked, then open the original posting to apply |
| **Secondary** | Students with little work experience | Read the job requirements clearly and know which information is missing before deciding to apply |

**Not served:** employers posting jobs, recruiting teams managing candidates, working professionals who need a full recruitment system.

## 4. Main flow

The user's main job: **find a suitable posting and open the original posting to apply.**

1. Open the site, type a keyword (for example "gia sư" — tutor, "thực tập marketing" — marketing intern) and pick a city. — *Screen 1*
2. Choose filters: job type (part-time / internship), location, pay; or tap a common need such as "Không yêu cầu kinh nghiệm" (no experience required) or "Ca linh hoạt" (flexible shifts). — *Screen 1*
3. Press **"Tìm việc"** (Find jobs). — *goes to Screen 2*
4. Scan the result list, comparing each posting's title, company, job type, location, pay, posting date and verification status. — *Screen 2*
5. If nothing fits, adjust the filter bar (job type, location, pay, experience), change the sort order, or go to the next page of results. — *Screen 2*
6. Click a posting to see its details: description, requirements, schedule, pay, and the **source information** panel (source, link to the original posting, time last checked, points to check yourself). — *goes to Screen 3*
7. Press **"Ứng tuyển tại nguồn"** (Apply at source) to go to the source website, confirm the posting is still open, and apply there.

None of this flow needs a login. A student with an account can press **"Lưu việc"** (Save job) on Screen 2 or 3 to come back to the posting later under **"Việc đã lưu"** (Saved jobs).

## 5. Scope

### Building

- A web interface that works on desktop and mobile, focused on part-time jobs and internships (with an extra "Toàn thời gian" / full-time option for final-year students).
- Search by keyword and city, with basic filters: job type, location, pay, experience.
- Job postings taken from source sites that allow it in their `robots.txt`, plus postings the team enters by hand; all stored in a database with one consistent structure.
- A detail page showing the source name, the link to the original posting, and when the system last checked it.
- A clear **"Nguồn không cung cấp"** (not provided by source) label wherever a field is missing.
- Basic handling of duplicate or possibly outdated postings, where the data source allows it.
- An **"Ứng tuyển tại nguồn"** (Apply at source) button that opens the original posting to see the latest information and apply.
- Simple student accounts (email and password), used only for the personal features below.
- **Save job** and a **Saved jobs** page.
- **A short profile:** field of study and available working times, used to pre-select search filters.
- **In-site notifications** (the bell icon) when a saved job changes status or its application deadline is close.
- A **"Báo cáo tin tuyển dụng đáng ngờ"** (Report suspicious posting) button: the student gives a reason, and the team uses the report to re-check the source.
- Static content pages: job-hunting safety guide, about, help, contact, privacy.

### Not building

- **No employer accounts:** no job posting, no candidate management.
- **No messaging or interview scheduling** between candidates and employers.
- **No auto-apply, no CV upload or storage:** the "Hồ sơ sẵn sàng" (profile ready) panel only reminds students to prepare their own CV.
- **No scam verdicts:** the site never declares a posting fraudulent or certainly legitimate; user reports never put a label on a posting by themselves.
- **No email or SMS notifications:** only in-site notifications.
- **No Google/Facebook login, no student identity verification.**
- **No AI prediction** of a candidate's chance of being hired.
- **No bulk scraping:** no harvesting data from many websites, no bypassing logins, CAPTCHAs, rate limits or other protections of a source.
- **No mobile app:** only a website that works on phones.
- **No TopCV replacement:** not a full recruitment system like TopCV or other large job sites.

## 6. Screens

The three screens are in [`wireframes/`](wireframes/), in the order of the main flow. All three share the same top bar: **Trang chủ** (Home, back to Screen 1), **Việc làm** (Jobs, to Screen 2), **Việc đã lưu** (Saved jobs), the notification bell and the account menu (profile, log out). The footer links to the static content pages. The "Dữ liệu minh họa" (sample data) strip only marks fake data in the mockup and is not part of the real site.

### Screen 1 — Search and filter

[`wireframes/01 - Job Search.png`](wireframes/01%20-%20Job%20Search.png)

This is the first screen a student sees when opening CampusJob Trust. The student wants to narrow down the kind of job they need: they type a keyword (job title or company name), pick a city, then tap filter groups for job type (part-time, internship, full-time), location (including Remote), pay, or a common need such as "Không yêu cầu kinh nghiệm" (no experience required) or "Ca linh hoạt" (flexible shifts). Below that, **Công việc nổi bật** (featured jobs) gives a quick look at a few postings; the footer reminds them to "check the source before applying". Pressing **"Tìm việc"** (Find jobs) or **"Xem tất cả"** (See all) goes to Screen 2; clicking a featured job card (or the arrow on it) goes straight to Screen 3 for that posting.

### Screen 2 — Search results

[`wireframes/02 - Search Results.png`](wireframes/02%20-%20Search%20Results.png)

The student is comparing the postings that match their conditions to decide which ones are worth a closer look. Each card shows the title, company, job type, location, pay, posting date and the status **"Chưa xác minh độc lập"** (not independently verified), so the student does not assume every posting is trustworthy. If the results don't fit, the student changes the keyword and presses **"Tìm kiếm"** (Search), adjusts the filter bar (job type, location, pay, experience), changes the sort order, or moves to another page. The **"Lưu việc"** (Save job) button on each card adds the posting to Saved jobs (login required). On the right, the **Hồ sơ sẵn sàng** (profile ready) panel links to the profile page through **"Hoàn thiện hồ sơ"** (complete your profile — field of study and available times; updating a CV is only a reminder), and the **Tìm việc an toàn** (job-hunting safely) panel links to the safety guide through **"Xem hướng dẫn an toàn"** (read the safety guide). Clicking a card goes to Screen 3 for that posting.

### Screen 3 — Job details and source check

[`wireframes/03 - Job Details & Source Trust.png`](wireframes/03%20-%20Job%20Details%20&%20Source%20Trust.png)

The student is deciding whether to apply for this posting. On the left are the job description, candidate requirements, schedule and location, and pay and benefits as stated in the posting. On the right is the **Thông tin nguồn tin** (source information) panel: the source name, the link to the original posting, when it was last checked and its update status, plus **Dấu hiệu cần kiểm tra** (things to check), which lists what the posting leaves out (for example "the posting does not mention a contract, pay schedule or hiring contact"), and a neutral "Before you apply" reminder. Pressing **"Ứng tuyển tại nguồn"** (Apply at source) or the source link opens the original website to see the latest information and apply there. **"Lưu việc làm"** (Save job) adds the posting to Saved jobs; **"Báo cáo tin tuyển dụng đáng ngờ"** (Report suspicious posting) opens a box for the reason on this same page. Pressing **"← Kết quả tìm kiếm"** (back to search results) returns to Screen 2 to look at another posting.
