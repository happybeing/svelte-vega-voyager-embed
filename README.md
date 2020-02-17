# Testing embedding of Vega Voyager in Svelte

This is part of the research for [Visualisation Lab](https://github.com/theWebalyst/visualisation-lab).

This repo is a simple test of embedding the Vega Voyager visualisation
and analysis tool in a Svelte project.

## Issues

- Voyager/README example has `require('voyager')` when it should be `require('datavoyager')`
- Voyager/package.json is missing dependencies `node-sass` `font-awesome` 
- Using webpack, need:
  - to install `file-loader` and `url-loader`
  - webpack.config.js needs `url-loader` and `file-loader` rules for `font-awesome`
- To load the test datasets need to... ??? `vega-datasets`
- Styles look broken in the 'Add dataset' popup, and on the dashboard etc.

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
