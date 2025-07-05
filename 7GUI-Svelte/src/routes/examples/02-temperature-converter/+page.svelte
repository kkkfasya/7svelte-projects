<script lang="ts">
	class Temperature {
		#celcius = $state(0);
		#fahrenheit = $state(0);

		get celcius() {
			return this.#celcius;
		}
		set celcius(c) {
			this.#celcius = c;
			this.#fahrenheit = c * (9 / 5) + 32;
		}

		get fahrenheit() {
			return this.#fahrenheit;
		}
		set fahrenheit(f) {
			this.#fahrenheit = f;
			this.#celcius = (f - 32) * (5 / 9);
		}
	}

	const t = new Temperature();
</script>

<div class="flex gap-9">
	<h4 class="text-white">Celcius</h4>
	<input type="number" bind:value={t.celcius} />
	<h4 class="text-white">=</h4>
	<input type="number" bind:value={t.fahrenheit} />
	<h4 class="text-white">Fahrenheit</h4>
</div>
