
<script>
	import { onMount } from 'svelte';
	import * as d3 from 'd3';

	let svg;
	const data = [
		{ x: 1, y1: 10, y2: 100 },
		{ x: 2, y1: 20, y2: 200 },
		{ x: 3, y1: 30, y2: 300 },
		{ x: 4, y1: 40, y2: 400 },
		{ x: 5, y1: 50, y2: 500 }
	];

	onMount(() => {
		const width = 500;
		const height = 300;
		const margin = { top: 20, right: 50, bottom: 30, left: 50 };

		const x = d3.scaleLinear()
			.domain(d3.extent(data, d => d.x))
			.range([margin.left, width - margin.right]);

		const yLeft = d3.scaleLinear()
			.domain([0, d3.max(data, d => d.y1)]).nice()
			.range([height - margin.bottom, margin.top]);

		const yRight = d3.scaleLinear()
			.domain([0, d3.max(data, d => d.y2)]).nice()
			.range([height - margin.bottom, margin.top]);

		const xAxis = g => g
			.attr("transform", `translate(0,${height - margin.bottom})`)
			.call(d3.axisBottom(x).ticks(width / 80));

		const yAxisLeft = g => g
			.attr("transform", `translate(${margin.left},0)`)
			.call(d3.axisLeft(yLeft));

		const yAxisRight = g => g
			.attr("transform", `translate(${width - margin.right},0)`)
			.call(d3.axisRight(yRight));

		const lineLeft = d3.line()
			.x(d => x(d.x))
			.y(d => yLeft(d.y1));

		const lineRight = d3.line()
			.x(d => x(d.x))
			.y(d => yRight(d.y2));

		const svgEl = d3.select(svg)
			.attr("width", width)
			.attr("height", height);

		svgEl.append("g").call(xAxis);
		svgEl.append("g").call(yAxisLeft);
		svgEl.append("g").call(yAxisRight);

		svgEl.append("path")
			.datum(data)
			.attr("fill", "none")
			.attr("stroke", "steelblue")
			.attr("stroke-width", 1.5)
			.attr("d", lineLeft);

		svgEl.append("path")
			.datum(data)
			.attr("fill", "none")
			.attr("stroke", "tomato")
			.attr("stroke-width", 1.5)
			.attr("d", lineRight);
	});
</script>

<svg bind:this={svg}></svg>