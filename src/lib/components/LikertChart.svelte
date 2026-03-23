<script>
	import * as Popover from '$lib/components/ui/popover/index.js';

	let {
		votes = {
			stronglyDisagree: 0,
			disagree: 0,
			neutral: 0,
			agree: 0,
			stronglyAgree: 0
		},
		classes = ''
	} = $props();

	let total = $derived(Object.values(votes).reduce((sum, current) => sum + current, 0));

	let widths = $derived(
		Object.fromEntries(Object.entries(votes).map(([key, value]) => [key, (value / total) * 100]))
	);
</script>

<div class={`flex h-10 overflow-hidden rounded ${classes}`}>
	<!-- Strongly Disagree -->
	<Popover.Root>
		<Popover.Trigger
			openOnHover
			closeDelay="0"
			openDelay="0"
			class="bg-tcf-red"
			style="width: {widths['stronglyDisagree']}%"
		></Popover.Trigger>
		<Popover.Content side="bottom" class="w-fit p-2">
			<p>
				<strong>Strongly Disagree:</strong>
				{votes.stronglyDisagree} votes ({((votes.stronglyDisagree / total) * 100).toFixed(2)}%)
			</p>
		</Popover.Content>
	</Popover.Root>

	<!-- Disagree -->
	<Popover.Root>
		<Popover.Trigger
			openOnHover
			closeDelay="0"
			openDelay="0"
			class="bg-red-300"
			style="width: {widths['disagree']}%"
		></Popover.Trigger>
		<Popover.Content side="bottom" class="w-fit p-2">
			<p>
				<strong>Disagree:</strong>
				{votes.disagree} votes ({((votes.disagree / total) * 100).toFixed(2)}%)
			</p>
		</Popover.Content>
	</Popover.Root>

	<!-- Neutral -->
	<Popover.Root>
		<Popover.Trigger
			openOnHover
			closeDelay="0"
			openDelay="0"
			class="bg-yellow-400"
			style="width: {widths['neutral']}%"
		></Popover.Trigger>
		<Popover.Content side="bottom" class="w-fit p-2">
			<p>
				<strong>Neutral:</strong>
				{votes.neutral} votes ({((votes.neutral / total) * 100).toFixed(2)}%)
			</p>
		</Popover.Content>
	</Popover.Root>

	<!-- Agree -->
	<Popover.Root>
		<Popover.Trigger
			openOnHover
			closeDelay="0"
			openDelay="0"
			class="bg-emerald-500"
			style="width: {widths['agree']}%"
		></Popover.Trigger>
		<Popover.Content side="bottom" class="w-fit p-2">
			<p>
				<strong>Agree:</strong>
				{votes.agree} votes ({((votes.agree / total) * 100).toFixed(2)}%)
			</p>
		</Popover.Content>
	</Popover.Root>

	<!-- Strongly Agree -->
	<Popover.Root>
		<Popover.Trigger
			openOnHover
			closeDelay="0"
			openDelay="0"
			class="bg-emerald-800"
			style="width: {widths['stronglyAgree']}%"
		></Popover.Trigger>
		<Popover.Content side="bottom" class="w-fit p-2">
			<p>
				<strong>Strongly Agree:</strong>
				{votes.stronglyAgree} votes ({((votes.stronglyAgree / total) * 100).toFixed(2)}%)
			</p>
		</Popover.Content>
	</Popover.Root>
</div>
