<script lang="ts">
	import { LightSwitch } from '@skeletonlabs/skeleton';
	export let data;
	console.log(data);

	let description = data.props.data.hourly[0].weather[0].main;
	let icon = data.props.data.hourly[0].weather[0].icon;
	let min = data.props.data.daily[0].temp.min;
	let max = data.props.data.daily[0].temp.max;
</script>

<div class="p-4">
	<LightSwitch />
</div>

<div class="card m-4 p-4 md:p-10 space-y-4 bg-white/20 dark:bg-black/20">
	{#if data}
		<header class="card-header">
			<div class="flex items-center justify-center">
				<p>Today</p>
			</div>
			<div class="flex items-center justify-center">
				<h1>Ottawa, ON</h1>
			</div>
		</header>

		<section class="p-4">
			<div class="flex items-center justify-center">
				<img src="https://openweathermap.org/img/wn/{icon}@2x.png" alt="" />
			</div>
			<div class="flex items-center justify-center">
				<h1>{description}</h1>
			</div>
		</section>

		<footer class="card-footer">
			<div class="p-4 md:p-10 space-y-4 bg-white/10 dark:bg-black/10">
				<div class="flex justify-center items-center mx-auto transition-[width] duration-200 w-full">
					<div class="w-full grid grid-cols-3 gap-4 place-items-center">
						<p>&#8593 <b>{max} &#8451</b></p>
						<span class="divider-vertical h-20" />
						<p>&#8595 {min} &#8451</p>
					</div>
				</div>
			</div>
		</footer>
	{/if}
</div>
