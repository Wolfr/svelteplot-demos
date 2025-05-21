

<header>
	<h1><a href="/">Svelteplot demos</a></h1>
</header>

<div class="container">

	<nav>
		<a href="/basics">Basics</a>
		<a href="/transforms">Transforms</a>
	</nav>

	<main>
		<slot />
	</main>
</div>

<style>

    :global(*) {
        box-sizing: border-box;
    }

    :global(html, body) {
        margin: 0;
        padding: 0;
    }

    :global(body) {
        font-family: sans-serif;
        line-height: 1.5;
    }

		header {
				max-width: 1280px;
				margin: 0 auto;
				padding: 1rem;
		}

		@media (min-width: 960px) {
				header {
						padding: 1rem;
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
				border: 1px solid black;
        border-bottom: none;
        max-width: 1280px;
				margin: 0 auto;
		}


    @media (min-width: 960px) {

        .container {
            display: flex;
        }
    }

    main {
				padding: 1.5rem;
		}

    @media (min-width: 960px) {

        main {
            flex-grow: 1;
        }
    }

		nav {
				width: 12rem;
				padding: 1.5rem;
				width: 100%;
        border: 1px solid black;
        border-width: 0 0 1px 0;
		}

    @media (min-width: 960px) {

        nav {
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
		}



</style>