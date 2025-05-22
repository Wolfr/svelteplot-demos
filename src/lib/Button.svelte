<script>
	export let href;
</script>

	<a class="button" {href}><slot /></a>

<style>

    .button {
				display: inline-block;
				text-decoration: none;
				background: #DDD;
				padding: .75rem 1rem;
				border-radius: 4px;
				color: #000;
    }

</style>
