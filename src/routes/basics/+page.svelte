<script>
	import { Plot, BarY, GridY, BarX } from 'svelteplot';
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
	<title>Basics - Wolfr Svelteplot Demos</title>
</svelte:head>

<h1>Basics</h1>

<h2>Vertical bar chart with label</h2>

<Plot grid y={{ label: 'Apples' }}>
	<BarY data={[1, 2, 3, 4, 10, 12, 15, 24]} fill="#4269D0" />
</Plot>

<pre><code>&lt;Plot grid y=&#123;&#123; label: &#39;Apples&#39; &#125;&#125;&gt;
	&lt;BarY data=&#91;1, 2, 3, 4, 10, 12, 15, 24&#93; fill=&quot;#4269D0&quot; /&gt;
&lt;/Plot&gt;</code></pre>

<h2>A horizontal bar chart</h2>

<Plot grid>
	<GridY strokeDasharray="1,3" strokeOpacity="0.3" />
	<BarX fill="#4269D0"  data={bears} x="count" y="name" />
</Plot>

<pre><code>&lt;Plot grid&gt;
	&lt;GridY strokeDasharray="1,3" strokeOpacity="0.3" /&gt;
	&lt;BarX fill="#4269D0" data=&#123;bears&#125; x="count" y="name" /&gt;
&lt;/Plot&gt;
</code></pre>

<h2>A horizontal bar chart with multiple colors</h2>

<Plot grid color={{ legend: true }}>
	<BarX data={myData} fill="name" y="name" x="value" />
</Plot>

<pre><code>&lt;Plot grid color=&#123;&#123; legend: true &#125;&#125;&gt;
	&lt;BarX data=&#123;myData&#125; fill="name" y="name" x="value" /&gt;
&lt;/Plot&gt;
</code></pre>


<h2>A vertical bar chart</h2>

<Plot grid color={{ legend: true }}>
	<BarY fill="#4269D0" data={bears2} y="value" x="name"  />
</Plot>

<pre><code>&lt;Plot grid color=&#123;&#123; legend: true &#125;&#125;&gt;
  &lt;BarY fill="#4269D0" data=&#123;bears2&#125; y="value" x="name"  /&gt;
&lt;/Plot&gt;
</code></pre>
<h2>A vertical bar chart with multiple colors</h2>


<Plot grid color={{ legend: true }}>
	<BarY fill="color" data={bears2} y="value" x="name"  />
</Plot>

<pre><code>&lt;Plot grid color=&#123;&#123; legend: true &#125;&#125;&gt;
  &lt;BarY fill="color" data=&#123;bears2&#125; y="value" x="name"  /&gt;
&lt;/Plot&gt;
</code></pre>

