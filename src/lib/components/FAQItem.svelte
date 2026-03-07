<script>
	import { createEventDispatcher } from 'svelte';
	import { slide } from 'svelte/transition';
	import { ArrowRight } from '@lucide/svelte';

	const dispatch = createEventDispatcher();

	export let question;
	export let answer;
	export let open = false;

	function toggle() {
		open = !open;
		dispatch('toggle', { isOpen: open });
	}
</script>

<div class="border-b border-gray-400 last:border-0">
	<button
		class="group flex w-full cursor-pointer items-center justify-between py-6 text-left transition-colors focus:ring-2 focus:ring-blue-500 focus:ring-offset-2 focus:outline-none"
		onclick={toggle}
		aria-expanded={open}
		aria-controls="answer-{question}"
	>
		<span class="text-lg font-semibold text-gray-900">
			{question}
		</span>
		<div
			class="ml-4 flex items-center text-gray-500 transition-transform duration-300"
			class:rotate-90={open}
		>
			<ArrowRight class="h-5 w-5" />
		</div>
	</button>

	<div class="overflow-hidden">
		{#if open}
			<div
				class="pb-6 pl-4 leading-relaxed text-gray-600"
				id="answer-{question}"
				transition:slide={{ duration: 300 }}
			>
				{answer}
			</div>
		{/if}
	</div>
</div>
