<script>
	let { text, fn } = $props();
</script>

<button
	onclick={fn}
	class="m-1 rounded border px-3 py-1 transition-all duration-200 hover:bg-black hover:text-white active:scale-110"
	>{text}</button
>
