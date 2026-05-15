# CMU Intent Robotics Lab Website

Static HTML website for the CMU Intent Robotics Lab (Interactive and Trustworthy Robotics Lab), hosted on GitHub Pages. No build system, no package manager — just plain HTML, CSS, and assets.

## Previewing

Open any `.html` file directly in a browser. No server or build step required.

## Structure

- `index.html` — home page with lab intro and news feed
- `people.html` — lab members by category (Director, PhD Students, etc.)
- `publications.html` — papers organized as Preprints then by year (newest first)
- `join.html` — recruitment/application info
- `research.html` — research overview (linked but currently commented out of nav)
- `stylesheet.css` — single shared stylesheet

Asset directories:

- `paper_imgs/` — paper thumbnails (PNG/GIF, displayed at 200px width)
- `ppl_imgs/` — people profile photos (displayed at 120px width, `border-radius:10%/10%`)
- `lab_event_imgs/` — lab social event photos
- `images/` — site logo, favicon, application domain illustration
- `pdf/` — hosted PDF files

## HTML Patterns

**Navigation header** is copy-pasted into every page (no templating). When updating nav links, update all pages.

**Custom HTML elements** used as styled display types (defined in `stylesheet.css`): `<heading>`, `<papertitle>`, `<profile-name>`.

**Publication entry** (one paper = one `<tr>` with two `<td>`):

```html
<tr>
  <td
    style="padding-left:20px;padding-bottom:20px;width:15%;vertical-align:middle"
  >
    <img
      src="paper_imgs/author_year.png"
      style="border-radius:5%/10%;width:200px"
    />
  </td>
  <td
    style="padding-left:35px;padding-bottom:20px;width:100%;vertical-align:left"
  >
    <papertitle>Title Here</papertitle>
    <br />
    A. Author, B. Author, A. Bajcsy
    <br />
    <em>Venue Name</em>, Year
    <br />
    <a class="button-paper" href="URL"
      ><i class="fa fa-file-text" aria-hidden="true"></i> paper</a
    >
    &nbsp
    <a class="button-website" href="URL"
      ><i class="fa fa-external-link"></i> website</a
    >
    <p></p>
  </td>
</tr>
```

Available button classes: `button-paper`, `button-website`, `button-video`, `button-code`. Icons use Font Awesome 4.7.

**Person entry** (one person = two `<td>` inside a nested `<table><tbody>`):

```html
<td
  style="padding-left:20px;padding-bottom:20px;width:15%;vertical-align:middle"
>
  <img src="ppl_imgs/name.jpg" style="border-radius:10%/10%;width:120px" />
</td>
<td
  style="padding-left:35px;padding-bottom:20px;width:100%;vertical-align:left"
>
  <profile-name>Full Name</profile-name>
  <br />
  <i>PhD Student</i>
  <br />
  <p></p>
  <a class="button-profile" href="URL"
    ><i class="fa fa-home" aria-hidden="true"></i
  ></a>
  &nbsp
  <a class="button-profile" href="mailto:email@andrew.cmu.edu"
    ><i class="fa fa-envelope"></i
  ></a>
  <br />
  <p></p>
</td>
```

**News items** in `index.html` use `<ul class="fa-ul">` with chevron icons and `[Mon Year]` date format.
