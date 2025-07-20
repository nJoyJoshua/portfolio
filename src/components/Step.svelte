<script lang="ts">
	export let step;
</script>

<a
	href={step.href}
	target="_blank"
	class="group flex cursor-pointer flex-col justify-between gap-4 rounded-lg border-2 border-solid border-violet-700 p-4 duration-200 hover:border-violet-400 sm:p-6 md:p-8"
>
	<div>
		<div class="mb-4 flex items-center">
			<img alt="App Icon" class="mr-4 h-10 w-10 rounded-lg" src={step.icon} />
			<div class="flex-grow">
				<h2 class="text-xl font-bold">{step.name}</h2>
				<span
					class="inline-flex items-center rounded-full bg-gray-100 px-2.5 py-0.5 text-xs font-medium text-gray-800"
				>
					{step.status}
				</span>
			</div>
		</div>
		<p class="mb-4">
			<slot />
		</p>
	</div>

	<div
		class="poppins group relative w-full cursor-pointer overflow-hidden rounded-full bg-white py-3 text-center text-base text-slate-950 sm:text-lg md:text-xl"
	>
		<div
			class="absolute top-0 right-full h-full w-full bg-violet-400 opacity-20 duration-200 group-hover:translate-x-full"
		></div>
		<span class="relative z-9">More Information &rarr;</span>
	</div>
</a>
