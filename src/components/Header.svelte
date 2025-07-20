<script lang="ts">
	export let y;

	let tabs = [
		{ name: 'Home', link: '#home' },
		{ name: 'Projects', link: '#projects' },
		{ name: 'About me', link: '#about' },
	];
</script>

<header
	class={'sticky top-0 z-[10] flex items-center justify-between border-b border-solid px-6 duration-200 ' +
		(y > 0 ? 'border-violet-950 bg-slate-950 py-4' : 'border-transparent bg-transparent py-6')}
>
	<h1 class="font-medium">
		<strong class="poppins text-xl font-bold">Joshua</strong> Freitag
	</h1>
	<div class="mr-4 ml-auto hidden items-center gap-4 sm:flex">
		{#each tabs as tab (tab.name)}
			<a href={tab.link} class="duration-200 hover:text-violet-400">
				<p>{tab.name}</p>
			</a>
		{/each}
	</div>
	<a
		href="https://www.linkedin.com/in/joshua-freitag-6565a0358/"
		target="_blank"
		class="blueShadow group relative overflow-hidden rounded-full bg-white px-5 py-2 text-slate-950"
	>
		<div
			class="Z-0 absolute top-0 right-full h-full w-full bg-violet-400 opacity-20 duration-200 group-hover:translate-x-full"
		></div>
		<h4 class="relative z-9">Get in touch</h4>
	</a>
</header>
