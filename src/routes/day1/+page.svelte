<script>
    import Button from '../../components/Button.svelte';
</script>

<div class="bg-cyan-200 h-screen">
	<div class="prose">
		<h1>Evan Ryu</h1>

		<div
			class="profile-image h-20 w-20 overflow-hidden rounded-full border bg-black bg-cover bg-center"
		></div>
		<div class="text-black">Evan</div>
		<div class="text-black">Student</div>

		<h2>About Me</h2>
		<p class="text-black">Hi my name is Evan.</p>
        <h2>Haiku</h2>
        <div class="bg-blue-500 text-center text-white">Storm clouds crack the sky</div>
        <div class="bg-blue-500 text-center text-white">Mountains tremble, rivers roar-</div>
        <div class="bg-blue-500 text-center text-white">Silence after rage</div>

        <h2>Components</h2>

        <Button text={'CLICK ME'} message={'I was clicked'} />
        <Button text={'DONT CLICK ME'} message={'Why did you click me?'} />
    </div>
</div>

<style>
	.profile-image {
		background-image: url('https://images.unsplash.com/photo-1754152728457-902f155ebcae?q=80&w=1466&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D');
	}
</style>
