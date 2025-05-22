
<script>
	import { Plot, Dot } from 'svelteplot';
	import simple from '$lib/layered-grammar-simple.csv.js';
</script>

<svelte:head>
	<title>Dot - Svelteplot - Demos</title>
</svelte:head>

<h1>Dot</h1>

<p>Dot is one of the possible “marks”.</p>

<Plot grid>
	<Dot data={simple.map(row => [row.A, row.C])} />
</Plot>
