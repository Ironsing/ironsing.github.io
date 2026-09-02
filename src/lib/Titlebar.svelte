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
		animated
	>
		<a href="/" class="flex items-center justify-center gap-4 px-6 py-4">
			<span class="text-xl font-light tracking-widest text-emphasis">ironsing.dev</span>
		</a>
	</BorderGlow>
</header>
