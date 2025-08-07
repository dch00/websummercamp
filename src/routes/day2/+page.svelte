<script>
	import Button from '../../components/Button.svelte';
	import LoadingBar from '../../components/LoadingBar.svelte';
	import HorseRace from './HorseRace.svelte';
	let progress = $state(10);

	function increment() {
		progress += 10;
		if (progress > 100) {
			progress = 100;
		}
	}
	function decrement() {
		progress -= 10;
		if (progress < 0) {
			progress = 0;
		}
	}
	function reset() {
		progress = 0;
	}

	// make decrement function with a button along with it
	// make a reset function that resets progress to 0
</script>

<HorseRace />

<Button text={'Increment'} fn={increment} />
<LoadingBar color={'bg-blue-500'} current={progress} max={100} />

<div class="bg-red-500 text-center transition-all duration-1000 hover:bg-blue-500 hover:text-left">
	https://tinyurl.com/btcasc
</div>

<div class="m-2 h-10 w-10 border transition-all duration-1000 hover:w-40">Box 1</div>
<div class="m-2 h-10 w-10 border transition-all duration-1000 hover:rounded-full">Box 2</div>
<div
	class="m-2 h-10 w-10 border transition-all duration-1000 hover:translate-x-96 hover:rotate-1080"
>
	Box 3
</div>
<div class="m-2 h-10 w-10 border transition-all duration-1000 hover:scale-150">Box 4</div>
