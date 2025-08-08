<script>
	import { onMount } from 'svelte';
	import ClickerGame from './day5/ClickerGame.svelte';
	import HorseRace from './day2/HorseRace.svelte';
	import SolarSystem from './day4-2/SolarSystem.svelte';
	
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
	<section class="relative h-screen flex items-center justify-center bg-gradient-to-b from-blue-300 via-blue-400 to-green-400">
		
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
			class="absolute top-20 right-20 w-24 h-24 bg-yellow-300 rounded-full shadow-lg opacity-90"
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
			<h1 class="text-6xl font-bold mb-4 drop-shadow-lg">Evan's Portfolio</h1>
			<p class="text-xl opacity-90 drop-shadow">Scroll down to explore the parallax effect</p>
			<div class="mt-8 animate-bounce">
				<svg class="w-8 h-8 mx-auto" fill="currentColor" viewBox="0 0 20 20">
					<path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
				</svg>
			</div>
		</div>
	</section>

	<!-- About Me (Profile picture, name, brief description) -->
	<section class="relative z-30 bg-gray-900 text-white">
		<div class="max-w-4xl mx-auto px-8 py-20">
			<div class="w-full bg-gray-700 p-2 rounded-full flex items-center">
				<div class="bg-gray-900 w-15 h-15 rounded-full flex justify-center items-center">
					<div class="bg-center bg-cover profile-image w-13 h-13 rounded-full"></div>
				</div>
				<div class="ml-2">
					<h2 class="text-4xl font-bold">Evan</h2>
					<div class="text-xs italic text-gray-400">Student</div>	
				</div>
			</div>
			<div class="grid md:grid-cols-2 gap-12">
				<div>
					<h3 class="text-2xl font-semibold mb-4 text-cyan-400">About Me</h3>
					<p class="text-lg leading-relaxed text-gray-300">
						Hi
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

    <!-- My projects -->
	<section class="relative z-30 bg-gray-800 text-white">
		<div class="max-w-4xl mx-auto px-8 py-20">
			<h2 class="text-4xl font-bold mb-8 text-center">My Projects</h2>
			<div class="flex flex-col space-y-5">
				<div class="text-center p-6 bg-gray-700 rounded-lg">
					<h3 class="text-xl font-semibold mb-3 text-blue-400">Clicker Game</h3>
					<div class="rounded overflow-hidden">
						<ClickerGame />
					</div>
					
				</div>
				<div class="text-center p-6 bg-gray-700 rounded-lg">
					<h3 class="text-xl font-semibold mb-3 text-green-400">Horse Race Simulator</h3>
					<div class="rounded overflow-hidden">
						<HorseRace />
					</div>
					
				</div>
				<div class="text-center p-6 bg-gray-700 rounded-lg">
					<h3 class="text-xl font-semibold mb-3 text-pink-400">Solar System</h3>
					<div class="rounded overflow-hidden">
						<SolarSystem />
					</div>
					
				</div>
			</div>
		</div>
	</section>

	<!-- Footer with scroll-to-top -->
	<section class="relative z-30 bg-black text-white text-center py-12">
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

	.profile-image {
		background-image: url(https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQd7W9OuM8FF6gUp59NpD8gZrpPWwd_ZFtrnQ&s);
	}
</style>
