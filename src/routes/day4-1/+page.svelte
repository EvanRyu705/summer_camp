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

<div>

    <section class="relative h-screen bg-gradient-to-b from-black via-blue-900 to-indigo-900 to-black flex justify-center items-center text-white">

        <!-- stars -->
        <div class="rounded-full w-1 h-1 bg-white/70 absolute top-10 left-15 animate-pulse"></div>
        <div class="rounded-full w-1 h-1 bg-white/80 absolute top-12 right-150 animate-pulse"></div>
        <div class="rounded-full w-1 h-1 bg-white/45 absolute top-25 left-45 animate-pulse"></div>
        <div class="rounded-full w-1 h-1 bg-white/90 absolute top-17 right-50 animate-pulse"></div>
        <div class="rounded-full w-1 h-1 bg-white/65 absolute top-40 left-100 animate-pulse"></div>
        <div class="rounded-full w-1 h-1 bg-white/55 absolute top-15 left-80 animate-pulse"></div>
        <div class="rounded-full w-1 h-1 bg-white/90 absolute top-22 left-135 animate-pulse"></div>
        
        <!-- moon -->
        <div 
        class="rounded-full w-35 h-35 bg-yellow-100/70 absolute top-10 right-10"
        style="transform: translateY({scrollY * 1.1})"  
        ></div>

        <!-- text -->
        <div>
            <div class="flex justify-center m-2 text-5xl font-bold">Night City {scrollY}</div>
            <div class="flex justify-center">Scroll down to explore the parallax effect</div>
            <div class="animate-bounce">
                <svg class="w-8 h-8 mx-auto" fill="currentColor" viewBox="0 0 20 20"> <path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
                </svg>
            </div>
        </div>

        
        <!-- mountain -->
            <div class="absolute -bottom-2 h-48 left-0 right-0 h-24">
                <svg viewBox="0 0 1200 200" class="w-full h-full">
	                <polygon 
                    points="0,200 0,120 200,60 400,100 600,40 800,80 1000,20 1200,60 1200,200" 
		            fill="#1e293b" opacity="0.7"
                />
            </svg>
        </div>

        <!-- buildings -->
        <div>
            <div class="absolute bottom-0 left-10 w-30 h-70 bg-gray-700">
                <div class="absolute left-5 top-10 w-5 h-5 bg-yellow-300"></div>
                <div class="absolute right-5 top-10 w-5 h-5 bg-yellow-300"></div>
                <div class="absolute left-5 top-20 w-5 h-5 bg-yellow-300"></div>
                <div class="absolute left-5 top-40 w-5 h-5 bg-cyan-200"></div>
                <div class="absolute right-5 top-30 w-5 h-5 bg-yellow-300/40"></div>
            </div>
            <div class="absolute bottom-0 right-10 w-30 h-70 bg-gray-700">
                <div class="absolute left-5 top-10 w-5 h-5 bg-yellow-300"></div>
                <div class="absolute right-5 top-10 w-5 h-5 bg-yellow-300"></div>
                <div class="absolute left-5 top-20 w-5 h-5 bg-yellow-300"></div>
                <div class="absolute left-5 top-40 w-5 h-5 bg-cyan-200"></div>
                <div class="absolute right-5 top-30 w-5 h-5 bg-yellow-300/40"></div>
            </div>
            <div class="absolute bottom-0 left-75 w-45 h-105 bg-gray-700">
                <div class="absolute left-10 top-15 w-7 h-7 bg-yellow-300"></div>
                <div class="absolute right-10 top-15 w-7 h-7 bg-yellow-300"></div>
                <div class="absolute left-10 top-30 w-7 h-7 bg-yellow-300"></div>
                <div class="absolute left-10 top-60 w-7 h-7 bg-cyan-200"></div>
                <div class="absolute right-10 top-45 w-7 h-7 bg-yellow-300/40"></div>
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