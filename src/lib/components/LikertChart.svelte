<script>
	import * as Tooltip from '$lib/components/ui/tooltip/index.js';

	let {
		votes = {
			stronglyDisagree: 10,
			disagree: 10,
			neutral: 10,
			agree: 10,
			stronglyAgree: 10
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
	<Tooltip.Root>
		<Tooltip.Trigger class="bg-tcf-red" style="width: {widths['stronglyDisagree']}%" title=""
		></Tooltip.Trigger>
		<Tooltip.Content side="bottom">
			<p>
				<strong>Strongly Disagree:</strong><br />
				{votes.stronglyDisagree} votes ({((votes.stronglyDisagree / total) * 100).toFixed(2)}%)
			</p>
		</Tooltip.Content>
	</Tooltip.Root>

	<!-- Disagree -->
	<Tooltip.Root>
		<Tooltip.Trigger class="bg-red-300" style="width: {widths['disagree']}%"></Tooltip.Trigger>
		<Tooltip.Content side="bottom">
			<p>
				<strong>Disagree:</strong><br />
				{votes.disagree} votes ({((votes.disagree / total) * 100).toFixed(2)}%)
			</p>
		</Tooltip.Content>
	</Tooltip.Root>

	<!-- Neutral -->
	<Tooltip.Root>
		<Tooltip.Trigger class="bg-yellow-400" style="width: {widths['neutral']}%"></Tooltip.Trigger>
		<Tooltip.Content side="bottom">
			<p>
				<strong>Neutral:</strong><br />
				{votes.neutral} votes ({((votes.neutral / total) * 100).toFixed(2)}%)
			</p>
		</Tooltip.Content>
	</Tooltip.Root>

	<!-- Agree -->
	<Tooltip.Root>
		<Tooltip.Trigger class="bg-emerald-500" style="width: {widths['agree']}%"></Tooltip.Trigger>
		<Tooltip.Content side="bottom">
			<p>
				<strong>Agree:</strong><br />
				{votes.agree} votes ({((votes.agree / total) * 100).toFixed(2)}%)
			</p>
		</Tooltip.Content>
	</Tooltip.Root>

	<!-- Strongly Agree -->
	<Tooltip.Root>
		<Tooltip.Trigger class="bg-emerald-800" style="width: {widths['stronglyAgree']}%"
		></Tooltip.Trigger>
		<Tooltip.Content side="bottom">
			<p>
				<strong>Strongly Agree:</strong><br />
				{votes.stronglyAgree} votes ({((votes.stronglyAgree / total) * 100).toFixed(2)}%)
			</p>
		</Tooltip.Content>
	</Tooltip.Root>
</div>
