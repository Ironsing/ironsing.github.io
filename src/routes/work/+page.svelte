<script lang="ts">
	import { Link } from '@lucide/svelte';
	import ElevatedCard from '$lib/ElevatedCard.svelte';
	import Hero from '$lib/Hero.svelte';

	const links = {
		ironsingDev: 'https://ironsing.github.io',
		ironsingDevWriteup: 'https://example.com',
		ezmic: 'https://github.com/Ironsing/ezmic',
		adhere: 'https://github.com/Ironsing/adhere'
	};
</script>

<main class="flex flex-1 flex-col items-center justify-center gap-10 p-4 py-20 lg:gap-20 lg:p-8">
	<Hero ruleWidth="w-xs lg:w-3xl">
		{#snippet heading()}
			<div class="text-3xl lg:text-7xl">stuff i've made (so far)</div>
		{/snippet}
	</Hero>

	<div class="flex w-full flex-wrap items-start justify-center gap-8">
		<ElevatedCard class="w-full max-w-80 p-8">
			<div class="flex max-w-3xs flex-col gap-3">
				<span
					class="flex items-center gap-2 font-serif text-2xl leading-none font-medium text-emphasis"
				>
					ironsing.dev
					<a href={links.ironsingDev} class="shrink-0" aria-label="project link">
						<Link class="h-4 w-4 text-site-gold" strokeWidth={2} />
					</a>
				</span>
				<span class="mt-3 text-xs font-medium tracking-[0.2em] text-site-gold uppercase"
					>problem statement</span
				>
				<span class="text-base text-normal">
					my work is too <i>private</i>. i want a public place to talk about it, and i want that
					place to be evidence that i <i>do things</i>.
				</span>
			</div>
		</ElevatedCard>
		<ElevatedCard class="w-full max-w-80 p-8">
			<div class="flex max-w-3xs flex-col gap-3">
				<span
					class="flex items-center gap-2 font-serif text-2xl leading-none font-medium text-emphasis"
				>
					ezmic
					<a href={links.ezmic} class="shrink-0" aria-label="project link">
						<Link class="h-4 w-4 text-site-gold" strokeWidth={2} />
					</a>
				</span>
				<span class="mt-3 text-xs font-medium tracking-[0.2em] text-site-gold uppercase"
					>problem statement</span
				>
				<span class="text-base text-normal">
					my phone contains some perfectly good mic hardware. why can't i use it with my computer as
					a normal mic?
				</span>
			</div>
		</ElevatedCard>
		<ElevatedCard class="w-full max-w-80 p-8">
			<div class="flex max-w-3xs flex-col gap-3">
				<span
					class="flex items-center gap-2 font-serif text-2xl leading-none font-medium text-emphasis"
				>
					Adhere
					<a href={links.adhere} class="shrink-0" aria-label="project link">
						<Link class="h-4 w-4 text-site-gold" strokeWidth={2} />
					</a>
				</span>
				<span class="mt-3 text-xs font-medium tracking-[0.2em] text-site-gold uppercase"
					>problem statement</span
				>
				<span class="text-base text-normal">
					there's no flawless sticky notes app for Hyprland that doesn't need you to change your
					hyprlang config.
				</span>
			</div>
		</ElevatedCard>
	</div>
</main>
