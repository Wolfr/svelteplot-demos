<!-- lib/components/Swatch.svelte -->
<script>
	export let name;
	export let hex;
</script>

<div class="swatch" title={name}>
	<div class="color" style="background-color: {hex}" />
	<span>{name}</span>
	<code>{hex}</code>
</div>

<style>
    .swatch {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 0.25rem;
        font-size: 0.8rem;
        width: 100px;
    }

    .color {
        width: 100%;
        height: 50px;
        border-radius: 6px;
        border: 1px solid #ccc;
    }

    code {
        font-family: monospace;
        color: #666;
    }
</style>
