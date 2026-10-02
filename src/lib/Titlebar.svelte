<script lang="ts">
	import BorderGlow from '$lib/BorderGlow.svelte';
	import StyledLink from '$lib/StyledLink.svelte';
	import { siteRed, siteGold, bg } from '$lib/design-tokens';
	import { Menu } from '@lucide/svelte';

	let open = $state(false);
</script>

<header class="relative z-30 w-full">
	<BorderGlow
		class="w-full"
		colors={[siteRed, siteGold]}
		backgroundColor={bg}
		borderRadius={0}
		interactive={false}
		animated
	>
		<div class="relative flex w-full items-center">
			<button
				type="button"
				class="absolute left-0 z-10 flex items-center px-6 py-4 text-emphasis lg:hidden"
				onclick={() => (open = !open)}
				aria-label="Toggle menu"
				aria-expanded={open}
			>
				<Menu class="h-5 w-5" />
			</button>

			<nav class="absolute left-0 hidden gap-4 px-6 py-4 text-normal lg:flex">
				<StyledLink href="/">home</StyledLink>
				<StyledLink href="/work">work</StyledLink>
				<StyledLink href="/writing">writing</StyledLink>
				<StyledLink href="/privacy">privacy</StyledLink>
			</nav>

			<a href="/" class="flex w-full items-center justify-center py-4">
				<span class="text-xl font-light tracking-tighter text-emphasis">ironsing.dev</span>
			</a>
		</div>
	</BorderGlow>

	{#if open}
		<nav
			class="absolute inset-x-0 top-full flex h-[calc(100vh-100%)] flex-col gap-6 bg-bg p-8 lg:hidden"
		>
			<StyledLink href="/" onclick={() => (open = false)}>home</StyledLink>
			<StyledLink href="/work" onclick={() => (open = false)}>work</StyledLink>
			<StyledLink href="/writing" onclick={() => (open = false)}>writing</StyledLink>
			<StyledLink href="/privacy" onclick={() => (open = false)}>privacy</StyledLink>
		</nav>
	{/if}
</header>
