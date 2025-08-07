<svelte:head>
	<link
		rel="stylesheet"
		href="https://www.gabriel-export.earth/html-energy-webring/onionring/styles.css"
	/>
</svelte:head>

<main
	class="flex h-screen w-full flex-col items-center justify-around border-20 border-double border-black"
>
	<div class="flex flex-col items-center justify-center p-8">
		<h1 class="p-8 text-4xl font-bold">Exporting Source into Form</h1>
		<div class="flex gap-2">
			<img src="/source.gif" class="mr-4 ml-2 h-20 w-auto" alt="Source" />
			<img src="/wave.gif" class="h-auto w-36" alt="Wave" />
			<img src="/form.gif" class="h-20 w-auto" alt="Form" />
		</div>
		<h2 class="pt-4 text-sm italic">Since 1995</h2>
	</div>
	<div class="flex flex-col items-center justify-center border-2 border-dotted border-black p-4">
		<h2 class="text-lg font-semibold">Find me online:</h2>
		<ul class="list-disc">
			<li>
				<a
					href="https://github.com/gchartier"
					class="text-blue-600 underline visited:text-purple-600 hover:text-blue-800">GitHub</a
				>
			</li>
			<li>
				<a
					href="https://x.com/gabriel_export"
					class="text-blue-600 underline visited:text-purple-600 hover:text-blue-800">Twitter</a
				>
			</li>
			<li>
				<a
					href="https://bsky.app/profile/gabriel-export.bsky.social"
					class="text-blue-600 underline visited:text-purple-600 hover:text-blue-800">Bluesky</a
				>
			</li>
		</ul>
	</div>

	<div id="html-energy-webring">
		<script
			type="text/javascript"
			src="https://www.gabriel-export.earth/html-energy-webring/onionring/variables.js"
		></script>
		<script
			type="text/javascript"
			src="https://www.gabriel-export.earth/html-energy-webring/onionring/widget.js"
		></script>
	</div>

	<div class="flex flex-col items-center justify-center gap-4 p-8">
		<img src="/under-construction.gif" class="h-12 w-auto" alt="Under Construction" />
		<p class="text-center text-sm">This site is under construction.</p>
		<p class="text-center text-sm">Please check back later.</p>
	</div>
</main>
