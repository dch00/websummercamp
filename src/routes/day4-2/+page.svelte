<div class="overflow-hidden relative h-screen bg-gradient-to-b from-black via-purple-900 to-black">
	<div class="centered h-8 w-8 rounded-full bg-yellow-200"></div>

	<!-- mercury -->
	<div
		class="centered h-12 w-12 animate-[spin_12s_linear_infinite] rounded-full border border-gray-200/40"
	>
		<div class="absolute h-2 w-2 translate-[4px] rounded-full bg-blue-300"></div>
	</div>

	<!-- earth -->
	<div
		class="centered h-18 w-18 animate-[spin_7s_linear_infinite] rounded-full border border-gray-200/40"
	>
		<div
			class="absolute h-2 w-2 translate-[9px] animate-[spin_1s_linear_infinite] rounded-lg bg-gradient-to-b from-blue-300 via-green-600 to-green-700"
		>
			<div class="h-1 w-1 -translate-[5px] rounded-full bg-white"></div>
		</div>
	</div>

	<!-- stars -->
	{#each Array(100) as _, i}
		<div
			class="absolute h-[0.5px] w-[0.5px] animate-pulse rounded-full bg-white/60"
			style="top: {Math.random() * 90}vh; left: {Math.random() *
				90}vw; animation-delay: {Math.floor(Math.random() * 250)}ms;"
		></div>
	{/each}
</div>
<!-- 
mercury 8s
venus 12s
earth 16s
mars 24s
jupiter 32s
saturn 40s -->

<style>
	.centered {
		@apply absolute top-1/2 left-1/2 -translate-1/2;
	}
</style>
