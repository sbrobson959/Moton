<script>
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';
	import { ArrowRight } from '@lucide/svelte';
	import { page } from '$app/stores';

	let { children } = $props();

	const PAGES = [
		['Home', '/'],
		['Frequently Asked Questions', '/faq'],
		['Take the Neighborhood Conditions Survey', '/survey'],
		['Apply for the Community Advisory Board', '/cab'],
		['View the Site Analysis', '/analysis']
	];
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>

<div class="w-full bg-tcf-bg-dark-gray px-8 pb-8 shadow-lg">
	<div class="flex max-w-120 gap-5 border py-5">
		<div class="flex flex-1 items-center">
			<img src="/logos/svg/Horizontal Color Light Pink.svg" alt="TCF logo" />
		</div>
		<div class="flex flex-1 items-center">
			<img src="/pt white.png" alt="PartnerTulsa logo" class="mx-auto max-h-full" />
		</div>
		<div class="flex flex-1 items-center">
			<img src="/kb light.png" alt="KB Advisors logo" />
		</div>
	</div>
	<h1 class="font-graebenbach-black text-5xl text-white">Dreaming Forward Together</h1>
	<h2 class="font-graebenbach-bold pt-2 text-4xl text-zinc-200">The Future of the Moton Site</h2>
	<div class="mt-5 ml-2 flex flex-col gap-1.5">
		{#each PAGES as [label, url]}
			{#if $page.url.pathname !== url}
				<a
					href={url}
					class="flex items-center gap-2 text-lg font-medium text-zinc-200 transition hover:text-white"
				>
					<ArrowRight />{label}
				</a>
			{/if}
		{/each}
	</div>
</div>

<div class="px-10 py-5">
	{@render children()}
</div>
