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
			<nav>
				<a href="/" class:selected={$page.url.pathname === '/'}>Intro</a>
				<a href="/basics" class:selected={$page.url.pathname === '/basics'}>Basics</a>
				<a href="/transforms" class:selected={$page.url.pathname === '/transforms'}>Transforms</a>
			</nav>
		</div>

		<main>
			<slot />
		</main>
	</div>
</div>

<style>


		header {
				margin: 0 auto;
				padding: 1rem 2rem;
				width: 100%;
        background: #FFF;
		}

		@media (min-width: 960px) {
				header {
						padding: .5rem 2rem;
						border: 1px solid black;
						border-bottom: none;
						border-top: none;
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
				border: 1px solid #000;
        border-bottom: none;
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

				width: 12rem;
				padding: 1.5rem;
				width: 100%;
        border: 1px solid black;
        border-width: 0 0 1px 0;
        background: #FFF;
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