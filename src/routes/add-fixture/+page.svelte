<script>
	import { onMount } from 'svelte';
	import toast, { Toaster } from 'svelte-french-toast';

	export let fixtureName = '';
	export let fixtureId = '';

	const inputFixtureName = (e) => {
		fixtureName = e.target.value;
	};

	const inputFixtureId = (e) => {
		fixtureId = e.target.value;
	};

	// onMount(() => {
	// 	toast.success('It works!');
	// });

	const handleClick = () => {
		if (fixtureName === '' || fixtureId === '') {
			toast.error('Incomplete information!');
			return;
		}
		toast.success('New fixture added!');
	};
</script>

<!-- <div class="form-control">
	<label class="label" for={id}>
		<span class="label-text">{label}</span>
	</label>
	<input {type} {placeholder} {id} {value} on:input={onInput} class="input input-bordered" />
	<button on:click={handleClick}> click me</button>
</div> -->
<div class="flex justify-center">
	<div class="card shadow-md bg-neutral-content mt-10 w-11/12 sm:w-4/12">
		<div class="card-body">
			<h2 class="card-title ">Add Fixture</h2>

			<div class="form-control w-full max-w-xs">
				<label class="label">
					<span class="label-text">Fixture Id</span>
				</label>
				<input
					type="text"
					placeholder="fixture id"
					class="input input-bordered w-full max-w-xs"
					on:input={inputFixtureId}
				/>
				<label class="label">
					<span class="label-text">Fixture name</span>
				</label>
				<input
					type="text"
					placeholder="fixture name"
					class="input input-bordered w-full max-w-xs"
					on:input={inputFixtureName}
				/>
			</div>
			<div class="card-actions justify-start">
				<button class="btn btn-primary" on:click={handleClick}>Add</button>
			</div>
		</div>
	</div>
	<Toaster />
</div>
