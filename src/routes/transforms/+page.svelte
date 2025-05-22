<script>
	import {Plot, RuleY, Line, mapY, windowY } from 'svelteplot';
	import aapl from '$lib/aapl.csv.js';
</script>

<svelte:head>
	<title>Transforms - Svelteplot - Demos</title>
</svelte:head>

<h1>Transforms</h1>

<p>See <a href="https://github.com/svelteplot/svelteplot/issues/10">#10</a>.</p>

<h2>Quantile</h2>

<p>Normalized between 0 and 1</p>

<Plot >
	<RuleY data={[0,1]} />
	<Line {...mapY({ data: aapl, x: 'Date', y:'Volume' }, 'quantile')}  />
</Plot>

<hr />

<h2>cumsum</h2>

<p>The cumsum option shows entries where every entry cumulatively gets added.</p>

<Plot >
	<RuleY data={[0,1]} />
	<Line {...mapY({ data: aapl, x: 'Date', y:'Volume' },
		'cumsum')} />
</Plot>

<hr />

<h2>rank</h2>

<p>The rank option shows all entries ranked.</p>

<p>Todo: figure out a good ranked visualisation</p>
<Plot>
	<Line {...mapY({ data: aapl, x: 'Date', y:'Volume' }, 'rank')}  />
</Plot>
