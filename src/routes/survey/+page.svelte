<script>
	import { onMount } from 'svelte';

	onMount(() => {
		const script = document.createElement('script');
		script.src = 'https://server.fillout.com/embed/v1/';
		script.type = 'text/javascript';
		document.head.appendChild(script);
	});
</script>

<div
	style="width:100%;height:500px;"
	data-fillout-id="56stgi9Uw7us"
	data-fillout-embed-type="standard"
	data-fillout-inherit-parameters
	data-fillout-dynamic-resize
></div>
