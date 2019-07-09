## React Chrome Extension Boilerplate

This boilerplate will get you up and running with a Chrome extension that uses: React, Redux and Redux Persist. The [Components](###Components) section will outline how this boilerplate is layed out and things you will want to remove if you do not want a particular feature.

### File Structure

This boilerplate is split up into various folders for organization. Below is an overview of these folders and what they do

```
boilerplate/
  app/               # This will store all of your JS files
  chrome/            # Chrome related assets
    icons/           # App icons
    scripts/         # Background and content scripts and stylesheets
    static/          # Entry points into your project
    manifest.json    # Your extensions manifest
  webpack.dev.js     # webpack config for dev enviorment
  webpack.prod.js    # webpack config for prod enviorment

```

### Getting Started

To get started, run `yarn` to install your dependencies. You should change your package `name` and `description` in `package.json`. Additionally, your should also change `name` `short_name` and `description` in your `manifest.json`

#### Package Scripts

`yarn dev` - will build the app in development and start the development server. After building the app, go to `chrome://extensions` and click "load unpacked extension" (development mode must be enabled). From here, load the `build` folder.

`yarn build` - will build the app in production

### Components

#### Background Scripts

This boilerplate comes with a background script in `chrome/scripts/background.js`. If you do not require background scripts, remove this file and also remove the following block from your manifest.json:

```js
  "background": {
    "scripts": ["background.js"],
    "persistence": false
  },
```

#### Content Scripts

Content scripts and stylesheets are located at `chrome/scripts/content.js` and `chrome/scripts/content.css` respectively. Remove these and then remove the following block in your manifest.json. Note that if you only need to remove one, simply remove the "css" or "js" line in the manifest. Additionally you should change the `matches` value to the site you are trying to run the content scripts on.

```js
  "content_scripts": {
    "matches": ["*"],
    "css": ["content.css"],
    "js": ["content.js"]
  },
```

#### Redux Devtools

#### Redux Persist
