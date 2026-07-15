# CourseMap

A self-contained academic dashboard for tracking grades, CGPA, degree progress, and course planning — built around North South University's BSCSE curriculum, but flexible enough to support any major.

No install, no server, no account. It's a single HTML file that runs entirely in your browser and saves data to your browser's local storage.

## Features

**Grade History**
- Log every course attempt by semester, credit hours, and grade
- Retakes are tracked automatically — the superseded grade is struck through, and only the best attempt counts toward CGPA, matching NSU's retake policy

**CGPA & Credit Tracking**
- Live CGPA calculation using best-attempt-per-course
- Credits earned vs. credits required, broken down by category (University Core, SEPS Core, CSE Major Core, Capstone, Major Elective, Open Elective)
- Estimated semesters remaining based on your target course load

**Curriculum Map**
- Every required course tagged as Completed, Available, Locked, or Retake Needed based on your actual prerequisite chain
- Major Elective courses are grouped into their trail segments (Algorithms & Computation, Software Engineering, Networks, Architecture & VLSI, Artificial Intelligence, plus Special Topics) so you can see trail progress at a glance

**Course Recommendations**
- Simulates future semesters, prioritizing pending retakes first, then courses that unlock the most future options
- Bundles lecture + lab pairs together automatically
- 0-credit labs (e.g. CSE225L, CSE311L) are folded into their parent course's line instead of cluttering the list, since they can't be taken independently

**Majors**
- Ships with the full BSCSE curriculum pre-loaded (134-credit hour NSU/ECE program)
- Build a custom major from scratch, or duplicate the built-in one and edit it — add/remove courses, categories, and prerequisites
- Switch which major's requirements power the Curriculum Map and Recommendations tabs without touching your Grade History

**Backup & Restore**
- Export all your data (grade history, custom majors, settings) to a single JSON file
- Import it back on any device/browser

## Getting Started

1. Download `coursemap.html`
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge) — double-click, or drag it into a browser tab
3. Start adding your course records under **Grade History**

That's it. Everything is saved automatically to your browser's local storage as you go.

### Hosting it (optional)

If you'd rather access it via a URL instead of a local file:

- **GitHub Pages** — push this repo and enable Pages in the repo settings; the file will be served at `https://<username>.github.io/<repo>/coursemap.html`
- Any static file host (Netlify, Vercel, a personal server) works the same way — it's just one HTML file with no build step and no backend

## Data & Privacy

All data lives in your browser's `localStorage`. Nothing is sent to a server — there is no backend. This means:

- Your data is private by default
- Clearing your browser's site data will erase it — **export a backup regularly**, especially before switching browsers/devices or clearing site data
- Data does **not** sync across browsers or devices unless you manually export/import

## Customization

- **Add a major**: go to the *Majors* tab → "+ New Custom Major", or duplicate the built-in BSCSE major and edit courses/categories from there
- **Add/edit courses**: within a custom major, use the course editor (code, name, credits, category, prerequisites, optional elective trail)
- **Adjust your target course load**: set "Target credits / semester" on the *Recommendations* tab to control how aggressively the semester plan is built

## Known Limitations

- The BSCSE curriculum data is built from NSU's published ECE department curriculum, but elective offerings and prerequisites can shift by catalog year — always cross-check anything borderline against your official advising sheet in RDS
- The recommendation engine is a heuristic based on prerequisite chains and category needs. It doesn't know real seat availability, which trimester a course is actually offered in, or your personal schedule constraints — treat it as a planning aid, not a substitute for academic advising
- No login or cloud sync — this is intentionally a local-first, single-user tool

## Tech Stack

Plain HTML, CSS, and vanilla JavaScript. No frameworks, no build step, no dependencies. Everything (course database, calculations, UI, storage) lives in one file for easy portability.

## License

Personal/educational use. Feel free to fork and adapt for your own university's curriculum.
