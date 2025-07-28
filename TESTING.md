# Testing and Bugfixing

During development, I utilized **[Chrome DevTools](https://developer.chrome.com/docs/devtools)** extensively for testing and debugging, especially across various screen sizes and devices. This iterative process helped identify and resolve numerous bugs, layout issues, and visual inconsistencies.

#### Fixed bugs and issues:

- **Issue:** ChatGPT placed curly typographic characters (`–`, `’`) in generated content, which could reduce screen reader compatibility and increase visual noise.
  - **Reason:** Generated content included non-standard typographic characters.
  - **Fix:** Replaced these characters with standard hyphens (`-`) and apostrophes (`'`).
- **Issue:** Tables, lists, and images had incorrect positioning due to excessive margins, and rows of images did not span the full width of the content section.
  - **Reason:** Each section had the `row` style class unnecessarily applied, causing incorrect alignment and spacing.
  - **Fix:** Removed the `row` CSS class from affected sections and adjusted alignment styling to ensure proper layout and responsiveness.
- **Bug:** Not all styles from `style.css` were being applied to their target elements.
  - **Reason:** The Bootstrap style link was placed lower in the HTML file, giving it higher priority and preventing custom styles from `style.css` from correctly overriding defaults.
  - **Fix:** Relocated the `<link>` tag for `style.css` in the HTML to appear _after_ the Bootstrap CSS link, ensuring it had higher specificity and correctly overrode Bootstrap defaults.
- **Issue:** On small screens, the World Records timeline table content would compress and take up twice as much vertical space, becoming less readable.
  - **Reason:** Default word wrapping within the table was causing content compression.
  - **Fix:** Disabled word wrap within the table and implemented a horizontal scroll bar that appears when the table content exceeds the screen width, preserving readability.
- **Issue:** Some image file sizes were unjustifiably large, impacting page load performance.
  - **Reason:** Images were in less efficient file formats, had low compression rates, and/or were at too high resolutions.
  - **Fix:** Resized all images to appropriate resolutions, applied compression, and converted them to the more efficient WebP file format.
- **Issue:** The W3C validator threw warnings about trailing slashes on void elements.
  - **Reason:** Prettier's default formatting options automatically added trailing slashes to void elements, which are not valid in HTML5.
  - **Fix:** Configured Prettier to set default formatter to `none` (or similar, depending on exact setup), manually removed trailing slashes, and then re-enabled Prettier's default formatter with `format on save mode` set as `modifications`.
- **Bug:** After deployment, navigation and all internal links were not working.
  - **Reason:** Invalid link formats were used for internal navigation.
  - **Fix:** Added `./` at the start of the `href` attribute for each internal link to ensure correct relative pathing on the deployed GitHub Pages site.
- **Bug:** After deployment, some images were not showing.
  - **Reason:** Invalid path formats were used for image file paths.
  - **Fix:** Removed the leading `/` from the `src` attribute of affected image file paths, correcting the relative pathing for deployment.
- **Bug:** The home navigation link on the website title was not working.
  - **Reason:** The link used an invalid `#` href.
  - **Fix:** Replaced `#` with `./` in the `href` attribute of the home navigation link, resolving the broken link.
- **Issue:** Lighthouse showed the Speedcubing page had a long initial loading time.
  - **Reason:** The embedded YouTube video player was loading immediately, contributing significantly to the initial page load.
  - **Fix:** Wrapped the embedded YouTube video player in a collapsible block, accessible via a button interaction, to reduce the initial load.
- **Bug:** The button designed to expand the collapsible video player was not functioning correctly.
  - **Reason:** Incorrect Bootstrap version 4 data attributes (`data-toggle`, `data-target`) were used instead of the required Bootstrap 5 syntax.
  - **Fix:** Replaced `data-toggle` and `data-target` with `data-bs-toggle` and `data-bs-target` correspondingly.
- **Bug:** Not all media query styles were applied correctly to pages at their corresponding resolutions.
  - **Reason:** Some media query styles were placed earlier in `style.css`, causing them to be overridden by later, more general styles.
  - **Fix:** Moved all media query styles to the very end of the `style.css` file to ensure they correctly overrode earlier styles and were applied at the intended breakpoints.

Beyond these, numerous smaller improvements and additional fixes are thoroughly documented in the project’s **commit history** for detailed reference.

#### Bugs to fix:

- Not found yet

## Validation

To ensure clean, standards-compliant code, I regularly used the **[W3C Web Validator extension](https://marketplace.visualstudio.com/items?itemName=CelianRiboulet.webvalidator)** in Visual Studio Code throughout the development process.

However, a few adjustments were needed to fully pass validation — here are the key fixes made:

- Removed all **trailing slashes** from void elements (`<meta>`, `<link>`, `<img>`, `<br>`) that were automatically added by Prettier — these are not valid in HTML5
- Found and corrected a **misspelled tag** that caused a validation warning
- Removed an invalid `<caption>` tag from the world records table
- Moved `iframe` borders from inline attributes to the external CSS file, as required for clean and valid markup

## Lighthouse

To evaluate and enhance the site’s performance, accessibility, best practices, and SEO, I ran **[Lighthouse](https://developer.chrome.com/docs/lighthouse)** audits using the deployed version on GitHub Pages. The final Lighthouse scores were all **97 or higher**.

![Lighthouse Report Screenshot](documentation/images/lighthouse.png)

Below is a breakdown of the optimizations made to achieve high scores in each Lighthouse category:

#### Performance

- Wrapped the human solve world record video player in a collapsible block to reduce initial page load
- Optimized `<iframe>` loading using `display: none` and `lazy loading` attributes
- Converted all `.jpg`/`.png` images to `.webp` format using WebP Converter
  - PNG images on the Solving page were excluded from conversion. Despite applying 75% quality compression, the file size reduction — from 7 KB to 6 KB — was deemed negligible and not worth the change.

#### Accessibility

- Replaced curly typographic characters (`–`, `’`) from generated content with standard hyphens (`-`) and apostrophes (`'`) to ensure screen reader compatibility and reduce visual noise
- Redesigned links in the world record table to be clearer and more accessible
- Darkened the footer copyright
  for better contrast and readability
- Reduced main heading font sizes to lessen visual strain on users

#### Best Practices

- I followed best practices throughout development, so there was very little that needed fixing during testing
- Resized the main page hero image for different breakpoints and implemented responsive delivery using `srcset`
- Replaced the active navigation link from an `<a>` tag with an empty `href` to a `<span>` element to prevent unnecessary page reloads

#### SEO

- Added a custom **meta description** to each page to improve indexing and discoverability by search engines
