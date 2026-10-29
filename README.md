# SodaMengu Farming Services: Website

A multi-page responsive website for SodaMengu Farming Services (Mengu, KwaZulu-Natal).

**Live site:** <add your Netlify / GitHub Pages link here>

## Pages
| File | Purpose |
|---|---|
| `index.html` | Home: hero, mission, dynamic "Farm notes" feed, FAQ accordion |
| `services.html` | Services with search, filter, sort and details modal |
| `about.html` | About, tabs (mission, vision, values), photo gallery with lightbox |
| `contact.html` | Contact details, interactive Leaflet map, message form that compiles an email |
| `enquiry.html` | Enquiry form with validation, cost estimate and AJAX submission |
| `style.css` | All styles (Part 2 plus Part 3 additions) |
| `js/main.js` | All JavaScript |
| `robots.txt`, `sitemap.xml` | SEO files |

## Changelog

### [Part 3]: Enhancing Functionality and SEO
**Date:** <add date> &nbsp; **Author:** <add your name>

#### Changes made from Part 2 feedback
<!-- Add one line per feedback point from your Part 2 marks sheet. Example format:
- Feedback: "<what the lecturer said>" → Change: <what you did and in which file>. -->
- Added the missing `<meta charset>` and `<meta name="viewport">` tags to every page. The Part 2 changelog said these were added, but the HTML files did not contain them, so responsive layout would not work on phones.
- Renamed files to lowercase, consistent names (`home.html` → `index.html`, `Service.html` → `services.html`, `About.html` → `about.html`, `Contact.html` → `contact.html`, `Farming_Services_Enquiry_Form.html` → `enquiry.html`). `index.html` is required for hosting platforms to show the site at its root address, and lowercase avoids broken links on case-sensitive servers. All internal links were updated.
- Added `lang`, `<meta name="description">`, descriptive `alt` text with `width`/`height` on images, a skip link and `aria-label` on the navigation.
- Removed inline styles from About and Services where a class could be used instead (`hero-slim`, `rounded-img`, `centered-note`).

#### Added: interactive elements (JavaScript)
- **Accordion** (home FAQ): accessible buttons with `aria-expanded`, animated open/close.
- **Tabs** (About): Mission / Vision / Values, with arrow-key, Home and End support.
- **Modal** (Services): native `<dialog>` showing service details and a link that pre-fills the enquiry form.
- **Interactive map** (Contact): Leaflet + OpenStreetMap marker at −27.090237, 32.267707 with a "Get directions" link and a fallback link if the map fails to load.
- **Gallery with lightbox** (About): 8 photos, previous/next buttons, arrow keys, Esc to close.
- **Animations and transitions**: CSS entrance on the home hero, accordion height transition, modal and lightbox fade/scale, hover zoom on gallery. All disabled under `prefers-reduced-motion`.
- **DOM manipulation**: services are filtered and re-ordered by moving existing card elements; results counts update live; modal content is built from the clicked card.

#### Added: dynamic content
- Home page "Farm notes" feed is generated from a JavaScript array, with a "Show more notes" button.
- Services page search box, type filter and A–Z / Z–A sort, with a live result count and an empty state with a "Clear filters" button.

#### Added: forms and validation
- **Enquiry form** (`enquiry.html`): enquiry type (services, products, volunteering, sponsorship); service checkboxes, farm size (number) and start date (date) for service enquiries. After validation the page shows a response: an indicative cost range with a per-service table, and an availability message based on the start date. Volunteer, sponsor and product enquiries each get their own response.
- **Contact form** (`contact.html`): name, email, phone, message type (select), subject, message (textarea with character counter), preferred contact (radio). After validation the message is compiled into an email (To, Subject, Body) and the user can open it in their email app (`mailto:` to the address in the code) or copy it.
- **Validation:** HTML5 attributes (`required`, `type`, `minlength`, `maxlength`, `min`, `max`) plus JavaScript checks: South African phone format, email format, name characters, number range, date not in the past, minimum message length.
- **Error handling:** inline error under each field, `aria-invalid`, a summary at the top with links to each problem, and focus moves to the first error.
- **AJAX submission:** the enquiry form uses `fetch()` with the form's `action` URL and shows sending / success / failure messages without reloading the page.

#### Added: SEO
- Unique `<title>` and `<meta name="description">` for every page; Open Graph tags.
- One `<h1>` per page with `h2`/`h3` hierarchy.
- Descriptive image file names where possible and descriptive `alt` text on every image.
- Internal linking in the nav, footer, hero buttons, FAQ answers and service modal.
- `LocalBusiness` structured data (JSON-LD) with address, coordinates, phone and hours on Home and Contact for local SEO.
- `robots.txt` and `sitemap.xml` created.
- Mobile-friendly (viewport tag, responsive layout, 44px+ touch targets for the main controls).
- Page speed: `loading="lazy"` on below-the-fold images, `defer` on scripts, `preconnect` for fonts, no JavaScript frameworks.
- Security: `rel="noopener"` on external links; user input is inserted with `textContent` (not `innerHTML`) so form text cannot inject HTML.

## Setup notes (to finish before submitting)
1. **Form endpoint:** in `enquiry.html`, replace `https://formspree.io/f/your-form-id` with your Formspree form URL. Until then the form runs in demo mode (it validates and shows the response but sends nothing).
2. **Prices:** the rates in `PRICING` at the top of `js/main.js` are placeholders. Replace them with real figures.
3. **Sitemap and robots:** replace `YOUR-USERNAME.github.io/YOUR-REPO` with your live URL.
4. **Deploy:** push to GitHub, then enable GitHub Pages (Settings → Pages → deploy from `main` branch, root folder) or drag the folder into Netlify.

## References
<!-- Complete this list in the referencing style your institution requires (e.g. IIE Harvard). -->
- Leaflet (2023) *Leaflet: an open-source JavaScript library for interactive maps*, version 1.9.4. Available at: https://leafletjs.com
- OpenStreetMap contributors (n.d.) *OpenStreetMap*. Available at: https://www.openstreetmap.org/copyright
- Google Fonts (n.d.) *Fraunces* and *Karla*. Available at: https://fonts.google.com
- MDN Web Docs (n.d.) *The dialog element*. Available at: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog
- W3C (2024) *WAI-ARIA Authoring Practices Guide: accordion and tabs patterns*. Available at: https://www.w3.org/WAI/ARIA/apg/
- Image sources: <list where each file in /IMG came from. Several look like third-party images (book covers, supermarket promotional photo, stock photos) and need proper attribution or replacement.>
