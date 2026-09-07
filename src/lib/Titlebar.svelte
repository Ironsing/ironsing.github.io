<script lang="ts">
	import BorderGlow from '$lib/BorderGlow.svelte';
	import { siteRed, siteGold, bg } from '$lib/design-tokens';
	import { Menu, X } from '@lucide/svelte';

	let open = $state(false);
</script>

<header class="w-full">
	<BorderGlow
		class="w-full"
		colors={[siteRed, siteGold]}
		backgroundColor={bg}
		borderRadius={0}
		glowRadius={0}
		interactive={false}
		animated
	>
		<div class="relative flex w-full items-center">
			<button
				class="absolute left-0 z-20 flex items-center px-6 py-4 sm:hidden"
				onclick={() => (open = !open)}
				aria-label="Toggle menu"
			>
				{#if open}
					<X class="h-5 w-5 text-emphasis" />
				{:else}
					<Menu class="h-5 w-5 text-emphasis" />
				{/if}
			</button>

			<nav class="absolute left-0 z-10 hidden items-center gap-4 px-6 py-4 sm:flex">
				<a
					href="/"
					class="text-site-gold underline decoration-site-gold/40 underline-offset-4 transition-colors duration-300 hover:decoration-site-gold"
					>home</a
				>
				<a
					href="/about"
					class="text-site-gold underline decoration-site-gold/40 underline-offset-4 transition-colors duration-300 hover:decoration-site-gold"
					>about</a
				>
			</nav>

			<a href="/" class="flex w-full items-center justify-center gap-4 px-6 py-4">
				<span class="text-xl font-light tracking-widest text-emphasis">ironsing.dev</span>
			</a>
		</div>
	</BorderGlow>

	{#if open}
		<button class="fixed inset-0 z-30 block cursor-default bg-black/50 sm:hidden" onclick={() => (open = false)} aria-label="Close menu"></button>
		<nav class="fixed left-0 top-0 z-40 flex h-full w-64 flex-col gap-4 bg-bg p-6 shadow-xl sm:hidden">
			<div class="flex items-center justify-between">
				<span class="text-lg font-light tracking-widest text-emphasis">ironsing.dev</span>
				<button onclick={() => (open = false)} aria-label="Close menu">
					<X class="h-5 w-5 text-emphasis" />
					</button>
			</div>
			<a
				href="/"
				class="text-site-gold underline decoration-site-gold/40 underline-offset-4 transition-colors duration-300 hover:decoration-site-gold"
				onclick={() => (open = false)}
				>home</a
			>
			<a
				href="/about"
				class="text-site-gold underline decoration-site-gold/40 underline-offset-4 transition-colors duration-300 hover:decoration-site-gold"
				onclick={() => (open = false)}
				>about</a
			>
		</nav>
	{/if}
</header>
