<script>
import {onMount} from 'svelte';

import {Voyager, CreateVoyager} from 'datavoyager';

onMount(() => {
  const container = document.getElementById("voyager-embed");
  const config = undefined;
  const data = undefined;
  const voyagerInstance = CreateVoyager(container, config, data);
});
</script>

<style>
	h1 {
		color: purple;
	}
</style>
<svelte:head>
<link rel="stylesheet" type="text/css" href="./style.css">
</svelte:head>

<h1>Vega Voyager embedded in Svelte</h1>
<p>
By theWebalyst.
Code: <a href="https://github.com/theWebalyst/svelte-vega-voyager-embed">github</a> 
Twitter: <a href="https://twitter.com/safepress">@safepress</a>
</p>

<div id='voyager-embed'></div>
