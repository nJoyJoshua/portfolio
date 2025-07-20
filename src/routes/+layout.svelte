<script lang="ts">
	import '../app.css';
	import '@fortawesome/fontawesome-free/css/all.min.css';
	import Header from '../components/Header.svelte';
	import Footer from '../components/Footer.svelte';

	let { children } = $props();

	let y: number = $state(0);
	let innerHeight = $state(0);
	let innerWidth = $state(0);

	function goTop() {
		document.body.scrollIntoView();
	}
</script>

<div class="relative flex min-h-screen w-full flex-col text-sm sm:text-base">
	<div
		class={'fixed bottom-0 z-[10] flex w-full p-10 duration-200 ' +
			(y > 0 ? ' pointer-events-auto opacity-100' : ' pointer-events-none opacity-0')}
	>
		<button
			aria-label="to top"
			onclick={goTop}
			class="ml-auto grid aspect-square cursor-pointer place-items-center rounded-full bg-slate-900 px-3 text-violet-400 hover:bg-slate-800 sm:px-4"
		>
			<i class="fa-solid fa-arrow-up"></i>
		</button>
	</div>
	<Header {y} />
	<div class="mx-auto max-w-[1400px]">
		{@render children()}
	</div>
	<Footer />
</div>

<svelte:window bind:scrollY={y} bind:innerHeight bind:innerWidth />
