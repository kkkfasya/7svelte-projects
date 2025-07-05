<script lang="ts">
	import Button from '$lib/components/ui/button/button.svelte';
	import type { Attachment } from 'svelte/attachments';

	type FlightOptions = 'one-way' | 'return';

	const handleSubmit = (e: Event) => {
		e.preventDefault();
		alert(`You have booked a ${selectedFlight} flight on ${startDate}`);
	};

	const getTodayDate = () => {
		const date = new Date();

		return date
			.toLocaleDateString('ja-JP', { year: 'numeric', month: '2-digit', day: '2-digit' })
			.split('/')
			.join('-');
	};

	let selectedFlight = $state<FlightOptions>('one-way');
	let startDate = $state(getTodayDate());
	let returnDate = $state(getTodayDate());

	$inspect({
		selectedFlight,
		startDate,
		returnDate
	});

	const disabledButtonTooltip: Attachment = (element: HTMLButtonElement) => {
		if (element.disabled) {
            return () => {
			element.setAttribute(
				'title',
				'Cant book return flight, return date is smaller than start date'
			);
            }
		}

	};
</script>

<form action="" onsubmit={handleSubmit}>
	<select name="" id="" bind:value={selectedFlight}>
		<option value="one-way" selected>One-way flight</option>
		<option value="return">Return flight</option>
	</select>

	<label for="">
		<span>Select the start date:</span>
		<input type="date" min={getTodayDate()} bind:value={startDate} required />
	</label>

	<label for="">
		<span>Select the return date:</span>
		<input
			type="date"
			min={getTodayDate()}
			bind:value={returnDate}
			disabled={selectedFlight !== 'return'}
		/>
	</label>

	<button
		type="submit"
		disabled={startDate === undefined || (selectedFlight === 'return' && returnDate < startDate)}
		>Book</button
	>
</form>

<style>
	form {
		width: 13rem;
		display: flex;
		flex-direction: column;
	}

	button {
		margin-top: 1rem;
		width: 5rem;
		align-items: end;
		margin-left: auto;
	}
</style>
