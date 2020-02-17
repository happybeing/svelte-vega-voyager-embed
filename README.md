# Testing embedding of Vega Voyager in Svelte

This repo shows how to embed the Vega Voyager visualisation
and analysis tool in a Svelte project, and is part of the research for [Visualisation Lab](https://github.com/theWebalyst/visualisation-lab).

I you just want to play with Voyager I recommend using the official deployment via
the Voyager [github](https://github.com/vega/voyager), and watching their OpenVizConf ~
presentation video (about 30 mins).

## Issues
Working locally with `yarn dev` is best because it allows you to load the test
datasets listed in the default 'Load' dialog. When deployed to the zeit-now service
this no longer works, and the only way to load data seems to be by uploading a file
from your local device.

You may notice a problem with the component not filling the screen and not resizing with
you browser window. I've left this as my purpose for the moment was just to learn how to
embed Voyager in Svelte, but feel free to submit a PR if you fix this or any other issues.

## Voyager Issues

- `voyager/README.md` example has `require('voyager')` but should be `require('datavoyager')`
- `voyager/package.json` is missing dependencies `node-sass` and `font-awesome` 

## To embed in Svelte
### Bundling with webpack
  - install modules `file-loader` and `url-loader`
  - add the `url-loader` and `file-loader` rules for `font-awesome` to your `webpack.config.js` 

### Styles
The voyager `styles.css` does not appear to be in the voyager project, so I copied `styles.css` and `styles.css.map` 
from `./node_modules/datavoyager/dist` and included `styles.css` using `<svelte:head>`

### Datasets
To load the test datasets offered in the default 'Load' dialog you need to clone `https://github.com/vega/vega-datasets` and:
  - make a copy of `vega-datasets/data` in `./public/datasets/data` (for production)
  - make a copy of `vega-datasets/data` in `./public/node_modules/vega-datasets/data` (for development)

To avoid having a duplicate copy of `data`, use a symbolic link for the second of the above.

## Get started

```bash
git clone https://github.com/theWebalyst/svelte-vega-voyager-embed
 svelte-vega-voyager-embed

cd svelte-vega-voyager-embed
```

Install the dependencies...

```bash
cd svelte-vega-voyager-embed
yarn
```

...then start webpack:

```bash
yarn dev
```

Navigate to [localhost:8080](http://localhost:8080). You should see each component produce output in the browser (and the browser console). Edit a component file in `src`, save it, and the page should reload with your changes.

## LICENSE

License: GPLv3 (see LICENSE)
