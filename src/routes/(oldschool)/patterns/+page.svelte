<svelte:head>
	<link rel="stylesheet" href="html-energy-webring/onionring/styles.css" />
	<script type="text/javascript" src="html-energy-webring/onionring/variables.js" defer></script>
	<script type="text/javascript" src="html-energy-webring/onionring/widget.js" defer></script>
</svelte:head>

<aside class="aside-banner">
	<p>
		This page was made during <a
			href="https://www.gabriel-export.earth/html-day-austin-2025"
			target="_blank">HTML Day Austin 2025</a
		>, a local event inspired by <a href="https://html.energy" target="_blank">HTML Energy</a>
	</p>
</aside>
<main>
	<div class="main-content-box">
		<h1>What is a Pattern?</h1>
		<p>There's actually a lot of different kinds out there...</p>

		<h2>Textiles, Fabrics, and Tiles</h2>
		<div class="flex-container">
			<div>
				<p>Maybe you think of plaid?</p>
				<img
					src="/patterns/plaid.gif"
					class="small-image"
					alt="a dog in a picnic basekt with a plaid blanket"
				/>
			</div>

			<div>
				<p>or houndstooth?</p>
				<img src="/patterns/houndstooth.gif" class="small-image" alt="houndstooth pattern" />
			</div>

			<div>
				<p>or some bathroom tiles?</p>
				<img src="/patterns/tiles.jpg" class="small-image" alt="houndstooth pattern" />
			</div>
		</div>

		<h2>Nature</h2>
		<p class="nature-intro">Maybe you might think of patterns in nature.</p>
		<div class="flex-container">
			<div>
				<p>Like the ripples in dunes...</p>
				<img
					src="/patterns/dunes.jpg"
					alt="sand dunes with ripples in the sand"
					class="large-image"
				/>
			</div>

			<div>
				<p>or the waves of the sea</p>
				<img src="/patterns/waves.gif" alt="a gif of waves in the sea" class="wave-image" />
				<p>
					or the spirals in shells <img
						src="/patterns/shell.webp"
						alt="a nautilus shell with the golden ratio spiral"
						class="large-image"
					/>
				</p>
			</div>

			<div>
				<p>
					or how lightning, tree roots, tree branches, and human veins all look the same. <span
						class="highlight-text">wtf is up with that</span
					>
				</p>
				<img
					src="/patterns/fractals.jpg"
					alt="examples of fractals in nature looking the same like tree roots, tree branches, rivers, lightning, and leaf veins"
					class="large-image"
				/>
			</div>
		</div>
	</div>
	<div id="html-energy-webring"></div>
</main>

<style>
	main {
		padding: 3rem;
		background-image: url('/patterns/bg.gif');
	}

	h1 {
		font-size: 3rem;
		font-weight: bold;
	}

	h2 {
		font-size: 2rem;
		margin-top: 2rem;
	}

	#html-energy-webring {
		width: fit-content;
		margin: 0 auto;
		margin-top: 2rem;
	}

	.aside-banner {
		border-bottom-width: 4px;
		border-bottom-color: black;
		background-color: #a3e635; /* lime-400 equivalent */
		padding: 0.5rem; /* p-2 equivalent */
		color: black;
	}

	.main-content-box {
		width: fit-content;
		background: lightgray;
		border-radius: 20px;
		padding: 2rem;
		border: 5px solid black;
	}

	.flex-container {
		display: flex;
		gap: 4rem;
	}

	.small-image {
		width: 10rem;
	}

	.large-image {
		width: 20rem;
	}

	.wave-image {
		width: 20rem;
		height: 3rem;
	}

	.nature-intro {
		padding-bottom: 1rem;
	}

	.highlight-text {
		background-color: yellow;
	}
</style>
