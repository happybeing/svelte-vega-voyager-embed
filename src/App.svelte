<script>
import {onMount} from 'svelte';

import {Voyager, CreateVoyager} from 'datavoyager';

const fixedData1 = {
  "values": [
    {"fieldA": "A", "fieldB": 28}, {"fieldA": "B", "fieldB": 55}, {"fieldA": "C", "fieldB": 43},
    {"fieldA": "D", "fieldB": 91}, {"fieldA": "E", "fieldB": 81}, {"fieldA": "F", "fieldB": 53},
  ]
};

const fixedData2 = {
  "values": [
    {"fieldA": "A", "fieldB": 28}, {"fieldA": "B", "fieldB": 55}, {"fieldA": "C", "fieldB": 43},
    {"fieldA": "G", "fieldB": 19}, {"fieldA": "H", "fieldB": 87}, {"fieldA": "I", "fieldB": 52}
  ]
};

let voyagerInstance;
let loadData;

function onLoadFixedData () {
  console.log('onLoadFixedData()');
  if (voyagerInstance !== undefined) {
  	loadData = loadData === fixedData1 ? fixedData2 : fixedData1;
    voyagerInstance.updateData(loadData);
  }
}

onMount(() => {
  const container = document.getElementById("voyager-embed");
  const config = undefined;
  const data = undefined;
  voyagerInstance = CreateVoyager(container, config, data);
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
<p><button on:click={() => onLoadFixedData()}>Load Fixed Data</button></p>

<div id='voyager-embed'></div>
