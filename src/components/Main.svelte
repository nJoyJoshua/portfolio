<script lang="ts">
	import Step from './Step.svelte';

	let steps = [
		{
			name: 'Developer Portfolio',
			icon: 'images/portfolio-icon.png',
			href: 'https://github.com/nJoyJoshua/portfolio',
			active: true,
		},
		{
			name: 'Snack Map',
			icon: 'images/snackmap-icon.png',
			href: 'https://github.com/tobkel/snackmap',
			active: false,
		},
	];

	let benefits = [
		{
			name: 'a pragmatic and driven developer',
			description:
				"Through my dual studies as a MATSE, I’ve built a solid foundation in programming — starting with theoretical basics at university and deepening my understanding through hands-on experience at work. I’m motivated by the idea that you can build complex systems from scratch, just by writing code. Currently, I work primarily with Spring Boot and Angular, but I also enjoy exploring new technologies like Swift and SvelteKit. I'm constantly looking to learn and improve.",
		},
		{
			name: 'a reliable and self-organized team player',
			description:
				'I take ownership of my work, organize myself well, and always aim to deliver more than just the bare minimum. I like to tackle problems first on my own, but i dont hesitate to ask colleagues when I really need to. I enjoy working in a team — ideally in pairs — because that’s when ideas flow and work becomes fun.',
		},
		{
			name: 'technically focused with an eye for UX',
			description:
				"I'm not a designer, but I care about good user experience. I draw inspiration from the work of others and utilize that to create interfaces that feel intuitive.. My strengths clearly lie in the technical part of development, but I always keep the end user in mind.",
		},
		{
			name: 'honest, direct and open to feedback',
			description:
				'I value clear and respectful communication. If something’s not working, I’ll speak up—politely but directly. I also appreciate constructive feedback, especially from people I look up to. It helps me grow and improve continuously.',
		},
	];
</script>

<main class="flex flex-1 flex-col p-4">
	<section id="home" class="grid grid-cols-1 gap-10 py-8 sm:py-14 lg:grid-cols-2">
		<div class="flex flex-col gap-6 text-center md:gap-8 lg:justify-center lg:gap-10 lg:text-left">
			<h2 class="text-4xl font-semibold sm:text-5xl md:text-6xl">
				Hi! I'm <span class="poppins text-violet-400">Joshua</span> <br />
				Full Stack <span class="poppins text-violet-400">Developer</span>
			</h2>
			<p class="text-base sm:text-lg md:text-xl">
				My <span class="poppins text-violet-400">favorite tech</span> includes Springboot, Angular, Swift
				& SupaBase
			</p>
			<a
				href="https://www.linkedin.com/in/joshua-freitag-6565a0358/"
				target="_blank"
				class="blueShadow poppins group relative mx-auto cursor-pointer overflow-hidden rounded-full bg-white px-6 py-3 text-base text-slate-950 sm:text-lg md:text-xl lg:mr-auto lg:ml-0"
			>
				<div
					class="Z-0 absolute top-0 right-full h-full w-full bg-violet-400 opacity-20 duration-200 group-hover:translate-x-full"
				></div>
				<h4 class="relative z-9">Get in touch &rarr;</h4>
			</a>
		</div>
		<div class="relative grid place-items-center">
			<div
				class="m-24 overflow-hidden rounded-full border-4 border-solid border-violet-400 shadow-2xl"
			>
				<img src="images/profile.png" alt="Profile" class="z-[2] max-h-[70vh] object-cover" />
			</div>
		</div>
	</section>

	<section id="projects" class="flex flex-col gap-24 py-20 lg:py-32">
		<div class="flex flex-col gap-2 text-center">
			<h6 class="text-lg sm:text-xl md:text-2xl">A selection of projects I've worked on</h6>
			<h3 class="text-3xl font-semibold sm:text-4xl md:text-5xl">
				Want a <span class="poppins text-violet-400">closer look</span>?
			</h3>
		</div>
		<div class="grid grid-cols-1 gap-12 lg:grid-cols-3 lg:gap-10">
			<Step step={steps[0]}>
				<p>
					This portfolio was built using <span class="text-violet-400">SvelteKit</span> to showcase
					my
					<span class="text-violet-400">projects, skills, and experience</span> as a developer.
					While building it, I deepened my understanding of modern frontend development and static
					site deployment with
					<span class="text-violet-400">Netlify</span>.
				</p>
			</Step>
			<Step step={steps[1]}>
				<p>
					SnackMap is a mobile app that <span class="text-violet-400"
						>connects vending machine providers with users</span
					>. It was developed in a university course using
					<span class="text-violet-400">SwiftUI, Supabase, and MapKit</span>. Through this project,
					I gained hands-on experience with mobile UI design and developing native iOS apps.
				</p>
			</Step>
		</div>
	</section>

	<!--	About me-->
	<section
		id="about"
		class="relative flex flex-col gap-8 py-20 pt-10 sm:gap-12 md:gap-14 lg:py-32 lg:pt-16"
	>
		<div
			class="relative flex flex-col gap-2 py-4 text-center before:absolute before:top-0 before:left-0 before:h-1.5 before:w-2/3 before:bg-violet-700 after:absolute after:right-0 after:bottom-0 after:h-1.5 after:w-2/3 after:bg-violet-700"
		>
			<h6 class="text-lg sm:text-xl md:text-2xl">Want to know more?</h6>
			<h3 class="text-3xl font-semibold sm:text-4xl md:text-5xl">
				A bit <span class="poppins text-violet-400">about</span> me.
			</h3>
		</div>
		<p class="poppins mx-auto text-lg font-semibold sm:text-xl md:text-2xl">I am . . .</p>
		<div class="mx-auto flex w-full max-w-[800px] flex-col gap-20">
			{#each benefits as benefit, index (benefit.name)}
				<div class="flex gap-6 sm:gap-8">
					<p class="poppins text-4xl font-semibold text-slate-500 sm:text-5xl md:text-6xl">
						0{index + 1}
					</p>
					<div class="flex flex-col gap-6 sm:gap-8">
						<h3 class="text-2xl sm:text-3xl md:text-5xl">
							{benefit.name}
						</h3>
						<p>{benefit.description}</p>
					</div>
				</div>
			{/each}
		</div>
	</section>
</main>
