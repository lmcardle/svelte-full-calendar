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
			initialView: 'dayGridWeek',
			headerToolbar: {
				left: 'prev,next',
				center: 'title',
				right: 'dayGridDay,dayGridWeek,dayGridMonth'
			},
			firstDay: 1,
			editable: true,
			events: [
				{
					id: '132',
					title: 'The quick brown fox jumpped over the moon',
					start: '2021-09-29',
					editable: true
				}
			]
		});
		calendar.render();
	});
</script>

<div bind:this={calendarEl} />
