{#snippet anchor()}
	<svg
		xmlns="http://www.w3.org/2000/svg"
		width="16"
		height="16"
		viewBox="0 0 16 16"
		fill="currentColor"
	>
		<path
			d="M3.75 2h3.5a.75.75 0 0 1 0 1.5h-3.5a.25.25 0 0 0-.25.25v8.5c0 .138.112.25.25.25h8.5a.25.25 0 0 0 .25-.25v-3.5a.75.75 0 0 1 1.5 0v3.5A1.75 1.75 0 0 1 12.25 14h-8.5A1.75 1.75 0 0 1 2 12.25v-8.5C2 2.784 2.784 2 3.75 2Zm6.854-1h4.146a.25.25 0 0 1 .25.25v4.146a.25.25 0 0 1-.427.177L13.03 4.03 9.28 7.78a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042l3.75-3.75-1.543-1.543A.25.25 0 0 1 10.604 1Z"
		></path>
	</svg>
{/snippet}

<div class="space-y-4">
	<h1 class="text-white">7GUIs</h1>

	<p class="text-white">
		This is the <a href="https://svelte.dev/">Svelte {@render anchor()}</a> implementation of the
		<a href="https://eugenkiss.github.io/7guis/">
			7GUIs: A GUI Programming Benchmark {@render anchor()}</a
		> tasks.
	</p>
</div>

<style>
	svg {
		display: inline;
		position: relative;
		top: 2px;
	}
</style>
