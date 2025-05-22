

<script>
	import Swatch from './Swatch.svelte';

	let observable10 = [
		{ name: "Blue", hex: "#4269D0" },
		{ name: "Orange", hex: "#EFB118" },
		{ name: "Red", hex: "#FF725C" },
		{ name: "Cyan", hex: "#6CC5B0" },
		{ name: "Green", hex: "#3CA951" },
		{ name: "Pink", hex: "#FF8AB7" },
		{ name: "Purple", hex: "#A463F2" },
		{ name: "Light Blue", hex: "#97BBF5" },
		{ name: "Brown", hex: "#9C6B4E" },
		{ name: "Gray", hex: "#9498A0" }
	];

</script>

<svelte:head>
	<title>Observable colors - Svelteplot demos</title>
</svelte:head>

<h1>Observable colors</h1>

<p>Here are the colors of observable10 in swatches:</p>

<div class="swatch-list">
	{#each observable10 as { name, hex }}
		<Swatch {name} {hex} />
	{/each}
</div>

<p>This palette is the default in Observable Plot.</p>

<style>
    .swatch-list {
        display: flex;
        flex-wrap: wrap;
        gap: 1rem;
        padding: 1rem;
    }
</style>
