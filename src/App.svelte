<script>
	let newItem = '';
	let items = [];

	function addToList(){
		items = [...items, {text: newItem, status: false}];
		newItem = '';
	}

</script>

<main>
	<h1>Todo List</h1>
	<input bind:value={newItem} type="text" placeholder="new item">
	<button on:click={addToList}>Add</button>
	<ul>
		{#each items as item}
		<li>
			{item.text}
		</li>
		{/each}
	</ul>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>