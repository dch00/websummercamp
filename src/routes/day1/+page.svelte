<script>
	import Button from '../../components/Button.svelte';
</script>

<div class="w-full bg-blue-300">
	<div class="prose p-5">
		<h1 class="text-center">David's Profile</h1>
		<hr />
		<div
			class="profile-image h-20 w-20 overflow-hidden rounded-full bg-black bg-cover bg-center"
		></div>
		<div>David Chang</div>
		<div>Programmer</div>

		<h2>About Me</h2>

		<p>Hi my name is david.</p>

		<h2>Haiku Exercise</h2>
		<div class="bg-white text-center text-blue-900">This is colored text</div>

		<h2>Components</h2>

		<Button text={'CLICK ME'} message={'I was clicked'} />
		<Button text={'DONT CLICK ME'} message={'Why did you click me?'} />
	</div>
</div>

<style>
	.profile-image {
		background-image: url('https://images.unsplash.com/photo-1505628346881-b72b27e84530?q=80&w=987&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D');
	}
</style>
