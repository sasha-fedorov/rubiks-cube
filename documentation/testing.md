# Testing and Bugfixing

During development, I used **[Chrome DevTools](https://developer.chrome.com/docs/devtools)** to test and debug the website across different screen sizes and devices. This helped identify and fix various layout bugs, alignment issues, and visual inconsistencies.

Many of these changes, along with smaller improvements, are documented in the project’s **commit history** for reference.


## Validation

To ensure clean, standards-compliant code, I regularly used the **[W3C Web Validator extension](https://marketplace.visualstudio.com/items?itemName=CelianRiboulet.webvalidator)** in Visual Studio Code throughout the development process.

However, a few adjustments were needed to fully pass validation — here are the key fixes made:
- Removed all **trailing slashes** from void elements (`<meta>`, `<link>`, `<img>`, `<br>`) that were automatically added by Prettier — these are not valid in HTML5
- Found and corrected a **misspelled tag** that caused a validation warning
- Removed an invalid `<caption>` tag from the world records table
- Moved `iframe` borders from inline attributes to the external CSS file, as required for clean and valid markup


## Lighthouse

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