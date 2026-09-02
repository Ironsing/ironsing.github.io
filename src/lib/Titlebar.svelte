<script lang="ts">
	import BorderGlow from '$lib/BorderGlow.svelte';
	import { siteRed, siteGold, bg } from '$lib/design-tokens';
</script>

<header class="w-full">
	<BorderGlow
		class="w-full"
		colors={[siteRed, siteGold]}
		backgroundColor={bg}
		borderRadius={0}
		interactive={false}
		animated
	>
		<div class="flex w-full items-center">
			<nav class="absolute left-0 flex gap-4 px-6 py-4">
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
</header>
