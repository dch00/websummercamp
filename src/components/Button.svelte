<script>
	let { text, message } = $props();

	function test() {
		alert(message);
	}
</script>

<button
	onclick={test}
	class="m-2 cursor-pointer rounded border bg-gradient-to-br from-blue-600 via-purple-400 to-orange-500 p-2 hover:animate-spin"
	>{text}</button
>
