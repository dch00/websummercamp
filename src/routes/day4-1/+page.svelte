<script>
	import { onMount } from 'svelte';
	
	let scrollY = 0;
	
	onMount(() => {
		const handleScroll = () => scrollY = window.scrollY;
		window.addEventListener('scroll', handleScroll);
		return () => window.removeEventListener('scroll', handleScroll);
	});
</script>

<svelte:window bind:scrollY />

<div class="relative overflow-hidden">
	<!-- Hero Section with Parallax Cityscape -->
	<section class="relative h-screen flex items-center justify-center bg-gradient-to-b from-purple-900 via-blue-900 to-indigo-900">
		
		<!-- Stars Background (slowest) -->
		<div 
			class="absolute inset-0 opacity-80"
			style="transform: translateY({scrollY * 0.1}px)"
		>
			<div class="absolute top-10 left-10 w-1 h-1 bg-white rounded-full animate-pulse"></div>
			<div class="absolute top-20 right-20 w-1 h-1 bg-white rounded-full animate-pulse delay-100"></div>
			<div class="absolute top-32 left-1/4 w-1 h-1 bg-white rounded-full animate-pulse delay-200"></div>
			<div class="absolute top-16 right-1/3 w-1 h-1 bg-white rounded-full animate-pulse delay-300"></div>
			<div class="absolute top-40 left-3/4 w-1 h-1 bg-white rounded-full animate-pulse delay-400"></div>
			<div class="absolute top-24 left-1/2 w-1 h-1 bg-white rounded-full animate-pulse delay-500"></div>
		</div>

		<!-- Moon (slow parallax) -->
		<div 
			class="absolute top-20 right-20 w-24 h-24 bg-yellow-100 rounded-full shadow-lg opacity-90"
			style="transform: translateY({scrollY * 0.2}px)"
		>
			<div class="absolute top-2 left-2 w-3 h-3 bg-yellow-50 rounded-full opacity-60"></div>
			<div class="absolute bottom-3 right-4 w-2 h-2 bg-yellow-50 rounded-full opacity-40"></div>
		</div>

		<!-- Far Mountains (medium parallax) -->
		<div 
			class="absolute bottom-0 left-0 right-0 h-48"
			style="transform: translateY({scrollY * 0.3}px)"
		>
			<svg viewBox="0 0 1200 200" class="w-full h-full">
				<polygon points="0,200 0,120 200,60 400,100 600,40 800,80 1000,20 1200,60 1200,200" 
					fill="#1e293b" opacity="0.7"/>
			</svg>
		</div>

		<!-- City Skyline (faster parallax) -->
		<div 
			class="absolute bottom-0 left-0 right-0 z-10"
			style="transform: translateY({scrollY * 0.5}px)"
		>
			<!-- Building 1 -->
			<div class="absolute bottom-0 left-10 w-20 h-64 bg-gray-800">
				<div class="absolute top-4 left-2 w-3 h-3 bg-yellow-300"></div>
				<div class="absolute top-4 right-2 w-3 h-3 bg-yellow-300"></div>
				<div class="absolute top-12 left-2 w-3 h-3 bg-yellow-300"></div>
				<div class="absolute top-20 right-2 w-3 h-3 bg-yellow-300"></div>
				<div class="absolute top-28 left-2 w-3 h-3 bg-blue-300"></div>
			</div>

			<!-- Building 2 (tallest) -->
			<div class="absolute bottom-0 left-40 w-24 h-80 bg-gray-700">
				<div class="absolute top-2 left-2 w-4 h-4 bg-red-400"></div>
				<div class="absolute top-2 right-2 w-4 h-4 bg-red-400"></div>
				<div class="absolute top-10 left-2 w-4 h-4 bg-yellow-300"></div>
				<div class="absolute top-10 right-2 w-4 h-4 bg-yellow-300"></div>
				<div class="absolute top-18 left-2 w-4 h-4 bg-green-300"></div>
				<div class="absolute top-18 right-2 w-4 h-4 bg-blue-300"></div>
				<div class="absolute top-26 left-2 w-4 h-4 bg-yellow-300"></div>
				<div class="absolute top-34 right-2 w-4 h-4 bg-purple-300"></div>
			</div>

			<!-- Building 3 -->
			<div class="absolute bottom-0 left-72 w-16 h-48 bg-gray-600">
				<div class="absolute top-4 left-1 w-2 h-2 bg-yellow-300"></div>
				<div class="absolute top-4 right-1 w-2 h-2 bg-yellow-300"></div>
				<div class="absolute top-12 left-1 w-2 h-2 bg-blue-300"></div>
				<div class="absolute top-20 right-1 w-2 h-2 bg-green-300"></div>
			</div>

			<!-- Building 4 -->
			<div class="absolute bottom-0 right-40 w-20 h-72 bg-gray-800">
				<div class="absolute top-6 left-2 w-3 h-3 bg-cyan-300"></div>
				<div class="absolute top-6 right-2 w-3 h-3 bg-cyan-300"></div>
				<div class="absolute top-16 left-2 w-3 h-3 bg-yellow-300"></div>
				<div class="absolute top-16 right-2 w-3 h-3 bg-yellow-300"></div>
				<div class="absolute top-26 left-2 w-3 h-3 bg-pink-300"></div>
				<div class="absolute top-36 right-2 w-3 h-3 bg-blue-300"></div>
			</div>

			<!-- Building 5 -->
			<div class="absolute bottom-0 right-10 w-18 h-56 bg-gray-700">
				<div class="absolute top-4 left-1 w-2 h-2 bg-orange-300"></div>
				<div class="absolute top-4 right-1 w-2 h-2 bg-orange-300"></div>
				<div class="absolute top-12 left-1 w-2 h-2 bg-yellow-300"></div>
				<div class="absolute top-20 right-1 w-2 h-2 bg-red-300"></div>
			</div>
		</div>

		<!-- Title Text (no parallax - stays fixed) -->
		<div class="relative z-20 text-center text-white">
			<h1 class="text-6xl font-bold mb-4 drop-shadow-lg">Night City</h1>
			<p class="text-xl opacity-90 drop-shadow">Scroll down to explore the parallax effect</p>
			<div class="mt-8 animate-bounce">
				<svg class="w-8 h-8 mx-auto" fill="currentColor" viewBox="0 0 20 20">
					<path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
				</svg>
			</div>
		</div>
	</section>

	<!-- Content Sections -->
	<section class="relative z-30 bg-gray-900 text-white">
		<div class="max-w-4xl mx-auto px-8 py-20">
			<h2 class="text-4xl font-bold mb-8">Welcome to the City</h2>
			<div class="grid md:grid-cols-2 gap-12">
				<div>
					<h3 class="text-2xl font-semibold mb-4 text-cyan-400">🏙️ Urban Life</h3>
					<p class="text-lg leading-relaxed text-gray-300">
						Experience the vibrant energy of city life where dreams meet reality. 
						Towering skyscrapers reach toward the stars, each window telling a unique story 
						of ambition, creativity, and human connection.
					</p>
				</div>
				<div>
					<h3 class="text-2xl font-semibold mb-4 text-purple-400">🌃 Night Lights</h3>
					<p class="text-lg leading-relaxed text-gray-300">
						As darkness falls, the city transforms into a symphony of light. 
						Neon signs dance across building facades, creating an electric atmosphere 
						that never sleeps.
					</p>
				</div>
			</div>
		</div>
	</section>

	<section class="relative z-30 bg-gray-800 text-white">
		<div class="max-w-4xl mx-auto px-8 py-20">
			<h2 class="text-4xl font-bold mb-8 text-center">City Features</h2>
			<div class="grid md:grid-cols-3 gap-8">
				<div class="text-center p-6 bg-gray-700 rounded-lg">
					<div class="text-4xl mb-4">🏢</div>
					<h3 class="text-xl font-semibold mb-3 text-blue-400">Skyscrapers</h3>
					<p class="text-gray-300">Magnificent towers that define the city skyline and house thousands of dreams.</p>
				</div>
				<div class="text-center p-6 bg-gray-700 rounded-lg">
					<div class="text-4xl mb-4">🚗</div>
					<h3 class="text-xl font-semibold mb-3 text-green-400">Transport</h3>
					<p class="text-gray-300">Efficient networks connecting every corner of the metropolitan area.</p>
				</div>
				<div class="text-center p-6 bg-gray-700 rounded-lg">
					<div class="text-4xl mb-4">🎭</div>
					<h3 class="text-xl font-semibold mb-3 text-pink-400">Culture</h3>
					<p class="text-gray-300">Rich arts, entertainment, and diverse communities creating vibrant neighborhoods.</p>
				</div>
			</div>
		</div>
	</section>

	<section class="relative z-30 bg-gray-900 text-white">
		<div class="max-w-4xl mx-auto px-8 py-20">
			<h2 class="text-4xl font-bold mb-8">The Parallax Effect</h2>
			<div class="prose prose-invert max-w-none">
				<h3 class="text-2xl font-semibold mb-4 text-yellow-400">🎨 What We're Learning</h3>
				<ul class="space-y-3 text-lg">
					<li><strong>CSS Transforms:</strong> <code class="bg-gray-700 px-2 py-1 rounded">transform: translateY()</code></li>
					<li><strong>Scroll Events:</strong> <code class="bg-gray-700 px-2 py-1 rounded">window.scrollY</code></li>
					<li><strong>Layering:</strong> <code class="bg-gray-700 px-2 py-1 rounded">z-index</code> and <code class="bg-gray-700 px-2 py-1 rounded">position: absolute</code></li>
					<li><strong>Gradients:</strong> <code class="bg-gray-700 px-2 py-1 rounded">bg-gradient-to-b</code></li>
					<li><strong>Animations:</strong> <code class="bg-gray-700 px-2 py-1 rounded">animate-pulse</code>, <code class="bg-gray-700 px-2 py-1 rounded">animate-bounce</code></li>
				</ul>

				<h3 class="text-2xl font-semibold mb-4 mt-8 text-green-400">🔧 How It Works</h3>
				<p class="text-lg text-gray-300">
					Different elements move at different speeds as you scroll, creating depth and immersion. 
					The stars move slowest, mountains medium speed, and buildings fastest, creating the illusion 
					of 3D space on a 2D screen!
				</p>
			</div>
		</div>
	</section>

	<!-- Footer with scroll-to-top -->
	<section class="relative z-30 bg-black text-white text-center py-12">
		<h3 class="text-2xl font-bold mb-4">Keep Exploring! 🚀</h3>
		<p class="text-gray-400 mb-6">Scroll back up to see the parallax effect in reverse</p>
		<button 
			on:click={() => window.scrollTo({ top: 0, behavior: 'smooth' })}
			class="px-8 py-3 bg-gradient-to-r from-blue-500 to-purple-500 rounded-full font-semibold hover:scale-105 transition-transform duration-200"
		>
			Back to Top ⬆️
		</button>
	</section>
</div>

<style>
	:global(html) {
		scroll-behavior: smooth;
	}
</style>
