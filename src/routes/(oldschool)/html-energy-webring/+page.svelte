<script lang="ts">
	const sites = [
		'https://www.gabriel-export.earth/html-energy-webring/',
		'https://callmecannibal.neocities.org/',
		'https://lyer-online.neocities.org/',
		'https://naes.tech/htarotml/',
		'https://naes.tech/htmlun/',
		'https://harriethw.github.io/html-day-bristol/',
		'https://frippenator.neocities.org/',
		'https://www.pixouls.xyz/',
		'https://www.gabriel-export.earth/patterns',
		'https://baccyflap.com/rsp',
		'https://killalocalpedophile.neocities.org/',
		'http://constcast.org/',
		'https://corktree.neocities.org/',
		'https://amalinalai.github.io/precipice/busstop',
		'https://troy-sucks.neocities.org/',
		'https://ragman.net',
		'https://croakego.neocities.org/',
		'https://www.starcrush.net/pages/main',
		'https://brisray.com/utils/webrings.htm',
		'https://lile5ko.me',
		'https://rayyan.nekoweb.org/',
		'https://willascool.neocities.org/',
		'https://moonlit.exposed/not-too-far-across-the-fence/',
		'https://elijahposttrash.neocities.org/',
		'https://cyanidefish.neocities.org/',
		'https://r.foo.ng',
		'https://xyzzyzzyzx.xyz/home.html',
		'https://devhank.neocities.org/sakuramiku/sakuramiku',
		'https://sumthing.neocities.org',
		'https://lunaseeker.com/',
		'https://austinhuang.me/',
		'https://astrma.stream/',
		'https://binomech.net',
		'https://crispypata.neocities.org/',
		'https://shens.world/',
		'https://interstellarshareware.net/webrings/',
		'https://www.juliannes.website/',
		'https://my-awesome-website.neocities.org',
		'https://sabrinaa.page',
		'https://ruinacchi.neocities.org/'
	];

	const indexDomain = 'https://www.gabriel-export.earth';

	interface Member {
		domain: string;
		sites: string[];
	}

	function buildMembersList(): Member[] {
		const membersList: Member[] = [];
		const index = {
			domain: 'index (gabriel-export.earth)',
			sites: sites.filter((site) => site.startsWith(indexDomain))
		};
		const memberSites = sites.filter((site) => !site.startsWith(indexDomain));

		for (const site of memberSites) {
			const hostname = getHostname(site);
			if (!membersList.find((member) => member.domain === hostname)) {
				membersList.push({
					domain: hostname,
					sites: [site]
				});
			} else {
				membersList.find((member) => member.domain === hostname)?.sites.push(site);
			}
		}

		membersList.sort((a, b) => a.domain.localeCompare(b.domain));

		return [index, ...membersList];
	}

	function getHostname(url: string) {
		try {
			const hostname = new URL(url).hostname;
			// Remove www. prefix if present
			return hostname.replace(/^www\./, '');
		} catch {
			// Fallback for malformed URLs - extract hostname manually
			const urlWithoutProtocol = url.replace(/^https?:\/\//, '');
			const hostname = urlWithoutProtocol.split('/')[0].split('?')[0].split('#')[0];
			return hostname.replace(/^www\./, '');
		}
	}
</script>

<svelte:head>
	<title>✳️ HTML Energy Webring ✳️</title>
	<link rel="stylesheet" href="html-energy-webring/onionring/styles.css" />
	<script type="text/javascript" src="html-energy-webring/onionring/variables.js" defer></script>
	<script type="text/javascript" src="html-energy-webring/onionring/widget.js" defer></script>
</svelte:head>

<div class="container">
	<header>
		<h1>✳️ HTML Energy Webring ✳️</h1>

		<div class="energy-orb-container">
			<div class="energy-orb"></div>
			<div class="rotating-ring"></div>
		</div>

		<div class="html-energy-text">
			Explore a humble undercurrent of the web that is full of <strong>energy</strong>, one
			hyperlink at a time.
			<span class="spinning-text">✳️</span>
		</div>
	</header>

	<main>
		<section class="widget">
			<h2>Widget</h2>
			<div id="html-energy-webring"></div>
		</section>

		<section class="members">
			<h2>Members (A to Z)</h2>
			<h3 class="members-count">{buildMembersList().length} Members!</h3>
			<ul class="members-list">
				{#each buildMembersList() as member (member.domain)}
					<li class="member-item">
						{#if member.sites.length === 1}
							<a href={member.sites[0]} target="_blank">{member.domain}</a>
						{:else}
							<details class="member-details">
								<summary>
									<span>
										<a href={member.sites[0]} target="_blank">{member.domain}</a>
									</span>
								</summary>
								<ul>
									{#each member.sites as site (site)}
										<li><a href={site} target="_blank">{site}</a></li>
									{/each}
								</ul>
							</details>
						{/if}
					</li>
				{/each}
			</ul>
		</section>

		<section class="join">
			<h2>Join</h2>
			<div>
				<a
					href="https://github.com/gchartier/html-energy-webring?tab=readme-ov-file#-how-to-join"
					target="_blank">Click here!</a
				>
			</div>
		</section>
	</main>

	<footer>
		<div class="construction">
			<img src="html-energy-webring/under-construction.gif" alt="Under Construction" />
		</div>

		<div class="html-energy-text">
			<p>
				Built with
				<a href="https://garlic.garden/onionring/" target="_blank">OnionRing.js</a>
			</p>
			<p>
				Inspired by the
				<a href="https://html.energy" target="_blank">HTML Energy</a>
				movement
			</p>
			<p>The web is still alive. Can you feel it?</p>
		</div>
	</footer>
</div>

<style>
	.container {
		background: #e9e9ec;
		color: #000000;
		font-family: 'Comic Sans MS', cursive, sans-serif;
		text-align: center;
		margin: 20px;
		line-height: 1.6;
		max-width: 800px;
		margin: 0 auto;
		padding: 20px;

		min-width: 100vw;
	}

	header {
		margin-bottom: 30px;
	}

	main {
		border: 3px dotted #000000;
		background: #e9e9ec;
		padding: 30px;
		margin: 20px auto;
		border-radius: 15px;
		box-shadow: 0px 0px 197px -32px rgba(6, 241, 3, 0.93);
		-webkit-box-shadow: 0px 0px 197px -32px rgba(6, 241, 3, 0.93);
		-moz-box-shadow: 0px 0px 197px -32px rgba(6, 241, 3, 0.93);
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		gap: 2rem;
		padding-bottom: 4rem;
		max-width: 800px;
	}

	h1,
	h2 {
		color: #000000;
		text-shadow: 2px 2px 4px #06f103;
		margin-bottom: 10px;
	}

	h1 {
		font-size: 2.5em;
	}

	h2 {
		font-size: 1.5em;
	}

	.energy-orb-container {
		position: relative;
		display: flex;
		justify-content: center;
		align-items: center;
		margin: 20px auto;
	}

	.energy-orb {
		width: 100px;
		height: 100px;
		background: radial-gradient(circle, #00ff00, #008800);
		border-radius: 50%;
		margin: 20px auto;
		animation: pulse 2s infinite;
		box-shadow: 0px 0px 197px 14px rgba(6, 241, 3, 0.93);
		-webkit-box-shadow: 0px 0px 197px 14px rgba(6, 241, 3, 0.93);
		-moz-box-shadow: 0px 0px 197px 14px rgba(6, 241, 3, 0.93);
		position: relative;
		z-index: 2;
	}

	.rotating-ring {
		position: absolute;
		width: 140px;
		height: 140px;
		border: 3px solid transparent;
		border-top: 3px solid #06f103;
		border-right: 3px solid #00ff00;
		border-bottom: 3px solid #06f103;
		border-left: 3px solid #00ff00;
		border-radius: 50%;
		animation: rotate 3s linear infinite;
		z-index: 1;
	}

	.rotating-ring::before {
		content: '';
		position: absolute;
		top: -5px;
		left: -5px;
		right: -5px;
		bottom: -5px;
		border: 2px solid transparent;
		border-top: 2px solid #ffff00;
		border-right: 2px solid #ffff00;
		border-radius: 50%;
		animation: rotate 2s linear infinite reverse;
	}

	@keyframes rotate {
		0% {
			transform: rotate(0deg);
		}
		100% {
			transform: rotate(360deg);
		}
	}

	@keyframes pulse {
		0% {
			transform: scale(1);
		}
		50% {
			transform: scale(1.1);
		}
		100% {
			transform: scale(1);
		}
	}

	.members-list {
		height: fit-content;
		width: fit-content;
		padding: 10px;
		margin: 0 auto;
		border: 3px dotted #000000;
		border-radius: 10px;
		background-color: #ffffff;
		list-style-type: none;
	}

	.members-count {
		padding-bottom: 0.5rem;
		margin-top: -0.5rem;
	}

	.member-item {
		position: relative;
		text-align: left;
		padding: 4px 0;
	}

	.member-details summary,
	.member-details summary span {
		cursor: cell;
	}

	summary:hover,
	details[open] summary {
		background-color: #e9e9ec;
		color: #70e106;
		padding-left: 4px;
		border-radius: 6px;
	}

	.member-details summary::marker {
		color: #06f103;
	}

	.join {
		width: fit-content;
		margin: 0 auto;
	}

	.join div {
		background-color: #ffffff;
		border: 3px dotted #000000;
		padding: 20px;
		border-radius: 10px;
	}

	footer {
		font-size: 12px;
		margin-top: 30px;
		color: #888888;
	}

	footer img {
		margin: 0 auto;
		width: 30rem;
	}

	footer p {
		color: black;
	}

	footer div {
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
	}

	.html-energy-text {
		color: #000000;
		font-size: 1.1em;
		margin: 20px 0;
		text-shadow: 0 0 10px #06f103;
	}

	.spinning-text {
		animation: spin 3s linear infinite;
		display: inline-block;
	}

	@keyframes spin {
		from {
			transform: rotate(0deg);
		}
		to {
			transform: rotate(360deg);
		}
	}

	.flashing-text {
		animation: flash 1s infinite;
	}

	@keyframes flash {
		0%,
		50% {
			opacity: 1;
		}
		51%,
		100% {
			opacity: 0.3;
		}
	}
</style>
