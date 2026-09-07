<script lang="ts">
	import { Book, Link } from '@lucide/svelte';

	const links = {
		ironsingDev: 'https://ironsing.github.io',
		ironsingDevWriteup: 'https://example.com',
		ezmic: 'https://github.com/Ironsing/ezmic',
		adhere: 'https://github.com/Ironsing/adhere'
	};
</script>

<main class="flex flex-1 flex-col items-center justify-center gap-4 p-8">
	<h1 class="font-serif text-6xl leading-tight font-medium text-emphasis">stuff i've made (so far)</h1>
	<div
		class="h-px w-3xl [background:linear-gradient(to_right,var(--color-site-red)_0_50%,var(--color-site-gold)_50%_100%)]"
	></div>
	<div class="flex w-full flex-wrap justify-center gap-8">
		<div
			class="flex w-80 flex-col gap-6 rounded-[18px] border border-white/15 bg-bg p-8 text-left shadow-[0_16px_40px_-8px_rgba(0,0,0,0.7)]"
		>
			<div class="flex max-w-3xs flex-col gap-3">
				<span
					class="flex items-center gap-2 font-serif text-2xl font-medium text-emphasis leading-none"
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
		</div>
		<div
			class="flex w-80 flex-col gap-6 rounded-[18px] border border-white/15 bg-bg p-8 text-left shadow-[0_16px_40px_-8px_rgba(0,0,0,0.7)]"
		>
			<div class="flex max-w-3xs flex-col gap-3">
				<span
					class="flex items-center gap-2 font-serif text-2xl font-medium text-emphasis leading-none"
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
		</div>
		<div
			class="flex w-80 flex-col gap-6 rounded-[18px] border border-white/15 bg-bg p-8 text-left shadow-[0_16px_40px_-8px_rgba(0,0,0,0.7)]"
		>
			<div class="flex max-w-3xs flex-col gap-3">
				<span
					class="flex items-center gap-2 font-serif text-2xl font-medium text-emphasis leading-none"
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
					there's no flawless sticky notes app for Hyprland that doesn't need you to change your config.
				</span>
			</div>
		</div>
	</div>
</main>
