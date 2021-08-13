# Custom Portal for ngxCoder

This script was forked from [Portal](https://github.com/TryGhost/Portal)

## Usage

Ghost automatically injects this Portal script on all sites running Ghost 4 or higher.

Alternatively, Portal can be enabled on non-ghost pages directly by inserting the below script on the page.

```html
<script defer src="https://unpkg.com/@tryghost/portal@latest/umd/portal.min.js" data-ghost="https://mymemberssite.com"></script>
```

The `data-ghost` attribute expects the URL for your site, which is the only input Portal needs to work with your site's membership data via Ghost APIs.

### Custom trigger button

By default, the script adds a default floating trigger button on the bottom right of your page which is used to trigger the popup on screen.

Its possible to add custom trigger button of your own by adding data attribute `data-portal` to any HTML tag on page, and also specify a specfic [page](https://github.com/TryGhost/Portal/blob/main/src/pages.js#L13-L22) to open from it by using it as `data-portal=signup`.

The script also adds custom class names to this element for open and close state of popup - `gh-portal-open` and `gh-portal-close`, allowing devs to update its UI based on popup state.

## Basic Setup

1. Clone this repository:

```shell
git clone https://github.com/ngxCoder/ngxCoder-Custom-Portal.git
```

2. Change into the new directory and install the dependencies:

```shell
cd portal
npm i
```

## Configure for production

#### In this repo(Portal):

- Run `npm run build` to create the minified bundle with your changes at `umd/portal.min.js`

#### In your theme(Ex. Lyra):

- Copy `portal.min.js` from above and paste it in your theme at `assets/built/portal.min.js`

#### In Ghost repo

- Update your `config.production.json` to add "portal" config which points url to built copy.

```json
    ...,
    "portal": {
        "url": "https://ngxcoder.dev/assets/built/portal.min.js"
    },
    ...
```

## Available Scripts

In the project directory, you can also run:

### `npm start`

Runs the app in the development mode.
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.
You will also see any lint errors in the console.

### `npm run build`

Creates the production single minified bundle for external use in `umd/portal.min.js`.

### `npm test`

Launches the test runner in the interactive watch mode.
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

## Learn More

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).
You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

# Copyright & License

Copyright (c) 2013-2021 Ghost Foundation - Released under the [MIT license](LICENSE).
