# 11ty-landing-page

A simple landing page built with 11ty and Tailwind CSS.

**Requirements:**

1. Eleventy (developed and tested with version 0.12.1)
2. Tailwind CSS

All other dependencies are either linked from a CDN or included in this repository.

**Setup:**

1. [Install node and npm](https://nodejs.org/en/download)
2. Fork, clone or download this repo, by [following Github's directions](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository)
3. `cd` into the root folder of this repo
4. run `npm install`
5. run `npm run serve`
6. open a browser and go to `http://localhost:8080`

**Change Content:**

Content is written using [markdown](https://commonmark.org/help/), which is also used within JIRA and GitHub, so you probably already know it.

- To change the list of attributes, edit `./src/_data/features.json`
- To change the welcome content, edit `./src/sections/about.md`

**Basic configuration:**

1. Eleventy -> `./.eleventy.js`
2. Tailwind -> `./tailwind.config.js`
3. Netlify -> `./netlify.toml`

CSS is built via PostCSS and based on `./src/_includes/css/_page.css`. Building CSS gets triggered by `./src/css/page.11ty.js` and Tailwind's config is set to JIT (see: [Tailwind docs](https://tailwindcss.com/docs/just-in-time-mode))

Please note that this CSS build _does not_ include the `normalize.css` file used for the 2 regular pages (imprint, privacy) - a minified production version is stored in `./src/static/css` and gets included in the build by default.

**Change Templates/Layout:**

Page structure and templates are stored in `./src/_layouts/` and can be edited there.

Best have a look at `./layouts/base.njk` first to understand how it all comes together - the page itself is constructed from partial templates stored in `./src/includes/` and each section has a corresponding template file (`section.**.njk`) stored there.

`index.njk` in `./src/` arranges everything, meaning that sections can be added/re-ordered/removed/... there.

**Change images:**

Images are stored in `./static/img/`; everything in there can be considered a placeholder that should eventually be replaced with your actual production images.
