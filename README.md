# ![favicon](./documentation/images/favicon-20-20.svg) 3x3 Rubik's Cube Website


## Description

This is a personal portfolio project for my course, focused on the **3×3 Rubik's Cube**.The website consists of three pages that introduce the cube, teach how to solve it, and explore the world of speedcubing.

![Responsive Mockup](./documentation/images/mockup.webp)


## Deployment

This website is **deployed using GitHub Pages** and can be accessed at: **[https://sasha-fedorov.github.io/rubiks-cube/](https://sasha-fedorov.github.io/rubiks-cube/)**

Deploying the static website using GitHub Pages was straightforward.
I navigated to the **Repository Settings**, then to the **Pages** section. There, I selected Deploy from a branch as the source, chose the **master** branch, kept the default root (/), and clicked **Save**. After a short wait, the website became accessible via the link provided above.

## Goals

- Practice HTML/CSS and content structure
- Present information in a clear, friendly tone
- Build a responsive, educational website with multiple pages


## Website Structure

### 1. **About the Cube**

An introduction to the Rubik's Cube:

- Brief history and invention by Ernő Rubik
- Cultural impact and popularity
- Fun facts and trivia
- Links to other pages

### 2. **How to Solve It**

Beginner-friendly solving guide based on the [SolveTheCube.com](https://solvethecube.com/) method:

- Step-by-step instructions (with image placeholders)
- Simplified explanations and tips
- Algorithm references
- Source credited at the top and bottom of the page

### 3. **Speedcubing & Records**

A look into the competitive side of cubing:

- Summarized timeline of world records from [WCA](https://www.worldcubeassociation.org/)
- Videos of the current fastest human and robot solves
- Profiles of notable cubers
- Fun records and robot achievements


## Tools & Services

- **[VS Code](https://code.visualstudio.com/)** — used as the main code editor for development
- **[Chrome DevTools](https://developer.chrome.com/docs/devtools)** — used for debugging, testing website features and responsiveness 
- **[Figma](https://www.figma.com/)** — used to create site favicon and documentation images
- **[ChatGPT](https://chat.openai.com/)** — helped generate written content (but not code) for the website pages and this README
- **[WebP Converter](https://developers.google.com/speed/webp)** — used to resize and compress images for web optimization
- **[Am I Responsive](https://ui.dev/amiresponsive)** — used to create website mockup for documentation


## Validation

I validated the deployed version of the website using the **official W3C tools**:

### HTML Validation
- [Home Page](https://validator.w3.org/nu/?doc=https%3A%2F%2Fsasha-fedorov.github.io%2Frubiks-cube%2F)
- [How to Solve Page](https://validator.w3.org/nu/?doc=https%3A%2F%2Fsasha-fedorov.github.io%2Frubiks-cube%2Fsolving.html)
- [Speedcubing Page](https://validator.w3.org/nu/?doc=https%3A%2F%2Fsasha-fedorov.github.io%2Frubiks-cube%2Fspeedcubing.html)

### CSS Validation
- [Main CSS File](https://jigsaw.w3.org/css-validator/validator?uri=https%3A%2F%2Fsasha-fedorov.github.io%2Frubiks-cube%2F&profile=css3svg&usermedium=all&warning=1&vextwarning=&lang=en)

**All tests passed with no errors or warnings**, as confirmed by the validation result links above.

You can find the validation-related fixes made during development by [this link](./documentation/testing.md#validation).

## Testing and Bugfixing

For detailed information about testing, bugfixing, validation, and performance improvements, please refer to **[testing.md](./documentation/testing.md)**.

## Lighthouse

To evaluate and enhance the site’s performance, accessibility, best practices, and SEO, I ran **[Lighthouse](https://developer.chrome.com/docs/lighthouse)** audits using the deployed version on GitHub Pages. The final Lighthouse scores were all **97 or higher**.

![Lighthouse Report Screenshot](./documentation/images/lighthouse.png)

Details on the improvements made to achieve high Lighthouse scores are available  [here](./documentation/testing.md#lighthouse).


## Credits

- Solving method and structure: [SolveTheCube.com](https://solvethecube.com/)
- World records and official data: [World Cube Association (WCA)](https://www.worldcubeassociation.org/)
- Photos, data tables, and record timelines sourced from [WCA](https://www.worldcubeassociation.org/) (used under fair use for educational purposes)
- Flag emojis representing competitors regions: [OpenMoji](https://openmoji.org/)


## License / Usage

This project is for **educational and non-commercial use only**.

All third-party data and images are credited to their original sources in [Credits](#credits).
