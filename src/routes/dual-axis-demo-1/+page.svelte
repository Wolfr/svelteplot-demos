<script>
	import { Plot, Line, AxisX, AxisY } from 'svelteplot';

	// Dataset 1: values between 0 and 1
	const dataLow = [
		{ x: 0, y: 0.5 },
		{ x: 1, y: 0.4 },
		{ x: 2, y: 0.6 },
		{ x: 3, y: 0.45 },
		{ x: 4, y: 0.55 }
	];

	// Dataset 2: values between 300 and 600
	const dataHigh = [
		{ x: 0, y: 350 },
		{ x: 1, y: 400 },
		{ x: 2, y: 500 },
		{ x: 3, y: 450 },
		{ x: 4, y: 550 }
	];
</script>

<Plot grid>

	<AxisX />
	<AxisY label="Low values (0–1)" />
	<AxisY side="right" label="High values (300–600)" />


	<Line data={dataHigh} x="x" y="y" yScale="right" stroke="tomato" strokeWidth={2} />
</Plot>

<Plot>

	<AxisX />
	<AxisY label="Low values (0–1)" />
	<AxisY side="right" label="High values (300–600)" />

	<!-- @todo how to map to 0-1 on y scale? -->
	<Line data={dataLow} x="x" y="y" stroke="steelblue" strokeWidth={2} />
</Plot>
