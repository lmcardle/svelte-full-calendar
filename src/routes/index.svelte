<script>
	import { onMount } from 'svelte';
	import { browser } from '$app/env';
	import { Calendar } from '@fullcalendar/core';
	import dayGridPlugin from '@fullcalendar/daygrid';

	let calendarEl;
	let calendar;

	onMount(async () => {
		await import('@fullcalendar/core/vdom');
		calendar = new Calendar(calendarEl, {
			plugins: [dayGridPlugin],
			initialView: 'dayGridMonth'
		});
		calendar.render();
	});
</script>

<div bind:this={calendarEl} />
