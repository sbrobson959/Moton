<script>
	let email = $state('');
	let submitted = $state(false);

	async function handleSubmit(e) {
		e.preventDefault();
		if (!email || submitted) return;

		const formData = new URLSearchParams();
		formData.append('entry.928207455', email);

		try {
			await fetch(
				'https://docs.google.com/forms/d/e/1FAIpQLSdEQkuc2biwdn8SN60fHZ88xI-zH7Dg3gex_QtmFnn4-_ijag/formResponse',
				{ method: 'POST', body: formData, mode: 'no-cors' }
			);
		} catch (_) {
			// fire-and-forget — can't read no-cors response
		}

		submitted = true;
	}
</script>

<div class="mx-auto max-w-4xl">
	<h2 class="font-graebenbach mb-5 text-5xl font-black">
		Help us reimagine what North Tulsa could look like.
	</h2>

	<div class="mb-5 rounded-xl bg-tcf-bg-dark-gray p-6 text-white">
		<h3 class="font-graebenbach-bold mb-2 text-2xl">Stay In The Loop</h3>
		<p class="mb-4 text-zinc-300">Sign up for updates on the Moton Site project.</p>
		<form onsubmit={handleSubmit} class="flex gap-3 max-sm:flex-col">
			{#if submitted}
				<p class="text-tcf-light-green text-lg">Thanks — you're on the list!</p>
			{:else}
				<input
					type="email"
					bind:value={email}
					placeholder="Enter your email"
					required
					class="flex-1 rounded-lg border border-zinc-600 bg-tcf-bg-gray px-4 py-2.5 text-white placeholder-zinc-400 focus:border-tcf-light-green focus:outline-none"
				/>
				<button
					type="submit"
					class="rounded-lg bg-tcf-light-green px-6 py-2.5 font-medium text-tcf-dark-green transition hover:bg-tcf-medium-green hover:text-white"
				>
					Sign Up
				</button>
			{/if}
		</form>
	</div>

	<div class="overflow-hidden rounded-xl">
		<img src="moton 3d.webp" alt="Moton Site Map" />
	</div>
</div>
