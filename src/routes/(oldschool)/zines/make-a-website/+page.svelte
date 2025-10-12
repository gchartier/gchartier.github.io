<script lang="ts">
</script>

<!-- 💠 Source: https://rowan.fyi/made/zine-machine/ -->

<svelte:head>
	<title>Make a Website!</title>
	<meta charset="utf-8" />
	<meta http-equiv="x-ua-compatible" content="IE=edge" />
	<meta name="viewport" content="width=device-width, initial-scale=1" />
	<link
		rel="icon"
		href="data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text y=%22.9em%22 font-size=%2290%22>✳️</text></svg>"
	/>
	<meta name="Description" content="A zine about making your own website in HTML." />
	<meta name="theme-color" content="#E8D9A6" />
</svelte:head>

<main class="zine">
	<header class="zine-page page-1">
		<div class="mx-auto mt-0 mb-6 flex flex-col items-center">
			<h1>🚧 Under Construction 🚧</h1>
			<p>Refresh this page in a couple days!</p>
			<p>
				End result will be like this <a href="https://rowan.fyi/made/zine-machine/" target="_blank"
					>Zine Machine</a
				>.
			</p>
		</div>
	</header>
	<section class="zine-page page-2"></section>
	<section class="zine-page page-3">
		<!-- TODO: Page 3 content here -->
	</section>
	<section class="zine-page page-4">
		<!-- TODO: Page 4 - that's the halfway point, you're nearly there! -->
	</section>
	<section class="zine-page page-5">
		<!-- TODO: You guessed it, page 5 content now -->
	</section>
	<section class="zine-page page-6">
		<!-- TODO: Page 6, this is the last "page" but you can still keep going -->
	</section>
	<section class="zine-page page-7">
		<!-- TODO: Page 7, this is the inside of the back cover -->
	</section>
	<footer class="zine-page page-8">
		<!-- TODO: You made it! Page 8, the back cover. Feel free to use this for attributions. Hey, let me know if you want a review. I'll give you ★★★★★ and an amazing quote -->
	</footer>
</main>

<style>
	/* These are just the article styles, so change these to whatever fits your theme! */

	/* Probably keep this one bit as is though, it's going to make arranging things in print easier for you! */
	* {
		box-sizing: border-box;
		margin: 0;
		padding: 0;
	}

	body {
		font-family: sans-serif;
	}

	h1 {
		color: black;
		text-align: center;
		font-size: 180%;
	}

	h2 {
		color: black;
		font-family: monospace;
		text-align: center;
		font-size: 140%;
		font-weight: bold;
		margin: 0.2rem 0 0 0;
		padding: 0.2rem 0 0.2rem;
	}

	h3 {
		background: black;
		color: #e8d9a6;
		font-family: monospace;
		text-align: center;
		font-size: 140%;
		font-weight: normal;
		margin: 0.2rem 0 0 0;
		padding: 0.2rem 0 0.2rem;
	}

	th {
		text-align: left;
		background: #c9daf8;
		color: #073763;
	}

	p {
		padding: 0.2rem;
		padding-top: 0.5rem;
		font-size: 105%;
	}

	ul {
		padding-left: 2rem;
		list-style: none;
	}

	.zine-li:before {
		content: '\21D2';
		margin-left: -20px;
		margin-right: 10px;
	}

	.zine-link {
		font-family: monospace;
		background: #c9daf8;
		color: #073763;
	}

	.captioned-img {
		object-fit: contain;
		max-height: 100%;
		max-width: 100%;
		padding: 0 2rem 0 2rem;
	}

	figcaption {
		font-family: monospace;
		font-size: 80%;
		font-style: italic;
		background: #c9daf8;
		color: #073763;
		margin: 0 1rem 0 1rem;
	}

	.full-img {
		object-fit: contain;
		max-height: 100%;
		max-width: 100%;
		padding: 1rem;
	}

	.mini-img {
		max-width: 10rem;
	}

	.glitchButton {
		float: left;
		padding: 1rem 0.5rem 0 0.5rem;
	}

	.cc-licence {
		float: right;
		margin: 1rem 0.5rem 0 0.5rem;
	}

	/* Any styles that you **only** want to appear on a device should go in here! */

	@media screen {
		body {
			max-width: 30rem;
			background: #e8d9a6;
			margin: auto;
		}

		.zine {
			background: #e8d9a6;
			padding: 10px;
			border-left: 4px solid #e2b015;
			border-bottom: 4px solid #e2b015;
		}

		.zine-page {
			margin-top: 10px;
		}
	}

	/* Any styles that you want to apply **just** when the zine is printed go in here! */

	@media print {
		body {
			font-size: 69%;
		}

		a {
			color: inherit;
			text-decoration: none;
		}

		.mini-img {
			max-width: 4.4rem;
		}

		/* The styles below here are specifically for creating the page layout.
       * -> DON'T CHANGE THESE <- unless you know what you're doing!
       */

		@page {
			size: landscape;
			margin: 0;
			bleed: 0;
		}

		.zine {
			width: 100vw;
			height: 100vh;
			display: grid;
			gap: 1.5px;
			background: lightgrey;
			grid-template-areas:
				'page-5 page-4 page-3 page-2'
				'page-6 page-7 page-8 page-1';
			grid-template-columns: repeat(4, 25%);
			grid-template-rows: repeat(2, 50%);
		}

		.zine-page {
			background: white;
			padding: 0.2rem;
			overflow: hidden;
		}

		.page-5,
		.page-4,
		.page-3,
		.page-2 {
			transform: rotate(180deg) translateX(-0.1px);
		}

		.page-1 {
			grid-area: page-1;
		}

		.page-2 {
			grid-area: page-2;
		}

		.page-3 {
			grid-area: page-3;
		}

		.page-4 {
			grid-area: page-4;
		}

		.page-5 {
			grid-area: page-5;
		}

		.page-6 {
			grid-area: page-6;
		}

		.page-7 {
			grid-area: page-7;
		}

		.page-8 {
			grid-area: page-8;
		}
	}
</style>
