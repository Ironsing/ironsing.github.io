<script lang="ts">
	import BorderGlow from '$lib/BorderGlow.svelte';
	import StyledLink from '$lib/StyledLink.svelte';
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
			<nav class="absolute left-0 flex gap-4 px-6 py-4 text-normal">
				<StyledLink href="/">home</StyledLink>
				<StyledLink href="/about">about</StyledLink>
			</nav>
			<a href="/" class="flex w-full items-center justify-center py-4">
				<span class="text-xl font-light tracking-tighter text-emphasis">ironsing.dev</span>
			</a>
		</div>
	</BorderGlow>
</header>
