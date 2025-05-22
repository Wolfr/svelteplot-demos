<script>
	import { page } from '$app/stores';
	import '$lib/screen.css'
</script>

<div class="main-flex-container">
	<header>
		<h1><a href="/">Svelteplot demos</a></h1>
	</header>

	<div class="container">

		<div class="nav-container">
			<h2>Basics</h2>
			<nav>
				<a href="/" class:selected={$page.url.pathname === '/'}>Intro</a>
				<a href="/basics" class:selected={$page.url.pathname === '/basics'}>Basics</a>
				<a href="/dot" class:selected={$page.url.pathname === '/dot'}>Dot</a>
			</nav>

			<h2>Work in progress (docs related)</h2>
			<nav>
				<a href="/transforms" class:selected={$page.url.pathname === '/transforms'}>Transforms</a>
			</nav>

			<h2>Work in progress (own experiment related)</h2>
			<nav>
				<a href="/double-axis" class:selected={$page.url.pathname === '/double-axis'}>Double axis</a>
				<a href="/observable-colors" class:selected={$page.url.pathname === '/observable-colors'}>Observable colors</a>
			</nav>
		</div>

		<main>
			<slot />
		</main>
	</div>

	<footer>
		<p>An experiment to learn <a href="https://svelteplot.dev/">SveltePlot</a> and the <a href="https://vita.had.co.nz/papers/layered-grammar.pdf">layered grammar of graphics</a> by <a href="https://github.com/Wolfr">Wolfr</a>. See <a href="https://github.com/Wolfr/svelteplot-demos">Github repo</a> for code.</p>
	</footer>
</div>

<style>

		footer {
				padding: 1rem;

		}

		footer a {
				color: #777;
		}

		header {
				margin: 0 auto;
				padding: 1rem 2rem;
				width: 100%;
        background: #FFF;
        border: 0;
        border-bottom: 1px solid #CCC;
    }

		@media (min-width: 960px) {
				header {
						padding: .5rem 2rem;
				}
		}

		header h1 {
				font-size: 1.5rem;
		}

    header h1 a {
        text-decoration: none;
        color: #000;
    }

		.container {
        max-width: 1280px;
				margin: 0 auto;
        width: 100%;
				flex-grow: 1;
		}


    @media (min-width: 960px) {

        .container {
            display: flex;
        }
    }

    main {
				padding: 1.5rem;
        background: #FFF;
		}

    @media (min-width: 960px) {

        main {
            flex-grow: 1;
            padding: 1.5rem 4rem 4rem;
        }
    }

		.nav-container {
				padding: 1.5rem;
        border-right: 1px solid #CCC;
        background: #FFF;
    }

		.nav-container h2 {
				font-size: 1rem;
		}

    @media (min-width: 960px) {
        .nav-container nav {
            position: sticky;
            top: 1rem;
        }

			.nav-container {
						width: auto;
            flex-shrink: 0;
						flex-basis: 16rem;
						border-width: 0 1px 0 0;
        }
    }

		nav a {
				text-decoration: none;
		}

		nav a {
				display: block;
				padding: 10px;
				color: #333;
				border-radius: 4px;
		}

    nav a.selected {
        background-color: #eee;
				color: #000;
    }



</style>