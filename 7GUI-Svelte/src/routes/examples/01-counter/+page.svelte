<script lang="ts">
	let counter = $state(0);
</script>

<div class="flex gap-2">
	<input type="number" disabled bind:value={counter} />
	<button onclick={() => (counter = counter + 1)}>Count +1</button>
	<button onclick={() => (counter = counter - 1)}>Count -1</button>
</div>
