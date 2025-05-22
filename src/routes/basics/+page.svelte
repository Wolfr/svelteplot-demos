<script>
	import { Plot, BarY, GridY, GridX, BarX } from 'svelteplot';
	import bears from '$lib/bears.csv';

	const bears2 = [{
		name: 'Polar',
		value: 12,
		color: 'lightgray'
	}, {
		name: 'Brown',
		value: 4,
		color: 'brown'
	}]


	const myData = [{
		name: 'a',
		value: 12,
	}, {
		name: 'b',
		value: 4,
	}]

</script>

<svelte:head>
	<title>Basics - Svelteplot - Demos</title>
</svelte:head>

<h1>Basics</h1>

<h2>A horizontal bar chart</h2>

<Plot grid>
	<GridY strokeDasharray="1,3" strokeOpacity="0.3" />
	<BarX fill="bluesteel"  data={bears} x="count" y="name" />
</Plot>

<h2>A horizontal bar chart with multiple colors</h2>

<Plot grid color={{ legend: true }}>
	<BarX data={myData} fill="name" y="name" x="value" />
</Plot>

<h2>A vertical bar chart</h2>

<Plot grid color={{ legend: true }}>
	<BarY fill="steelblue" data={bears2} y="value" x="name"  />
</Plot>

<h2>A vertical bar chart with multiple colors</h2>

<Plot grid color={{ legend: true }}>
	<BarY fill="color" data={bears2} y="value" x="name"  />
</Plot>


