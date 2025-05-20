<script>
	import { Plot, BarY, BarX } from 'svelteplot';
	import bears from '$lib/bears.csv';
	import bears2 from '$lib/bears2.csv';
</script>

<h1>Svelteplot demos</h1>

<h2>A horizontal bar chart</h2>

<Plot grid>
	<BarX data={bears} x="count" y="name" />
</Plot>

<h2>A vertical bar chart</h2>

<Plot grid>
	<BarY data={bears} y="count" x="name" />
</Plot>

<Plot grid>
	<BarY data={bears2} x="count" y="name" />
</Plot>

<style>

	:global(body) {
			font-family: sans-serif;
	}

</style>