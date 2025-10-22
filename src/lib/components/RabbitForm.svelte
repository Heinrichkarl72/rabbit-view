<script>
	import { serverAddress, store } from '$lib/store.svelte.js';

	let name = $state('');

	async function addRabbit() {
		await store.addRabbit(name);
		name = '';
		store.listRabbits();
	}
</script>

<input type="text" bind:value={name} class="text-black" />
<div>{name}</div>
<button class="btn btn-primary" onclick={addRabbit}>Add Rabbit!</button>
