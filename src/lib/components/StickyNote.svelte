<!-- 💠 Source: https://gist.github.com/SimonPadbury/fc55c054c0480550c3be592111778763 -->

<script lang="ts">
	import MagicTechnology from '$lib/icons/MagicTechnology.svelte';

	let props = $props();
</script>

<div class="sticky flex flex-col items-center {props.class}">
	<span>Any sufficiently</span>
	<span>advanced technology</span>
	<span>is indistinguishable</span>
	<span>from magic.</span>
	<span class="font-bold">
		- <a href="https://en.wikipedia.org/wiki/Clarke%27s_three_laws" target="_blank">
			Arthur C. Clarke
		</a>
	</span>
	<MagicTechnology class="mx-auto fill-gray-600" width="30pt" height="30pt" />
</div>

<style>
	.sticky {
		position: absolute;
		right: 0;
		z-index: 150;
		transform: rotate(5deg);
		width: fit-content;
		min-height: 150px;
		margin: -10px 10px 10px;
		padding: 1rem 1rem 0.5rem 1rem;
		font-family: 'Comic Sans MS', 'Comic Sans', 'Chalkboard SE', 'Comic Neue', cursive;
		font-size: 14px;
		color: #000;
		background: rgba(255, 255, 51, 1);
		box-shadow: -2px 2px 2px rgba(0, 0, 0, 0.3);
	}
	.sticky:before,
	.sticky:after {
		content: '';
		display: block;
		position: absolute;
		width: 16px;
		height: 16px;
		top: 0;
		right: 0;
	}
	.sticky:before {
		border-top: solid 8px #fff;
		border-right: solid 8px #fff;
		border-left: solid 8px transparent;
		border-bottom: solid 8px transparent;
	}
	.sticky:after {
		border-bottom: solid 8px #dddd33;
		border-left: solid 8px #dddd33;
		border-right: solid 8px transparent;
		border-top: solid 8px transparent;
	}
</style>
