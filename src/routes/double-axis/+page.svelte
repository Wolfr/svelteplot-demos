<script>
	import { Plot, Line, AxisX, AxisY, GridX, GridY } from 'svelteplot';
	import { csvParse, autoType } from 'd3-dsv';

	const data = csvParse(`A,B,C
2,3,10
1,2,12
4,5,18
9,10,22`, autoType);
</script>

<Plot axes={0}>
	<AxisX />

	<AxisY axis="left" />
	<AxisY axis="right" />

	<Line data={data} x="A" y="B" stroke="steelblue" />
	<Line data={data} x="A" y="C" yScale="right" stroke="tomato" />
</Plot>

