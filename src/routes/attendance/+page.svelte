<script lang="ts">
	import type { PageData } from './$types';
	import students from '$lib/sample_attendance.json';
	let { data }: { data: PageData } = $props();
</script>

<head>
	<title>Attendance</title>
</head>
<main>
	<div class="main-container w-[100%]">
		<h2 class="text-2xl font-bold text-rose-800">Attendance Statistics</h2>
		<div class="w-[100%]">
			<table class="attendance-table w-[100%] rounded-lg bg-rose-100 text-rose-900">
				<thead class="text-center">
					<tr class="font-semibold">
						<td class="p-2">S. No</td>
						<td class="p-2">Name</td>
						<td class="p-2">Time of Entry</td>
						<td class="p-2">Attendance</td>
					</tr>
				</thead>
				<tbody class="text-center">
					{#each students as student, i}
						<tr>
							<td class="p-2">{i + 1}</td>
							<td class="p-2">{student.name}</td>
							<td class="p-2">{student.time}</td>
							<td class="p-2">{student.attendance}</td>
						</tr>
					{/each}
				</tbody>
			</table>
		</div>
	</div>
</main>

<style lang="scss">
</style>
