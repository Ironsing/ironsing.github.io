<script lang="ts">
	import ElevatedCard from '$lib/ElevatedCard.svelte';
	import Hero from '$lib/Hero.svelte';
	import StyledLink from '$lib/StyledLink.svelte';
	import { siteRed, siteGold } from '$lib/design-tokens';
</script>

<main class="flex h-full w-full flex-col items-center justify-center gap-20 px-6 py-20">
	<Hero>
		{#snippet heading()}
			hey, i’m <StyledLink href="/about">Aayush Digikar.</StyledLink>
		{/snippet}
		{#snippet lead()}
			<p class="max-w-xl text-lg text-normal">
				i like doing things. feel free to take a gander below.
			</p>
		{/snippet}
	</Hero>

	<section class="flex w-full max-w-3xl flex-row items-stretch justify-center gap-6">
		<ElevatedCard
			href="/work"
			colors={[siteGold]}
			glowColor="45 90 60"
			class="group h-full w-full sm:w-72"
		>
			<div class="flex h-full items-center justify-between gap-6 p-8 text-left">
				<div class="flex flex-col gap-2 text-normal">
					<span class="flex items-center gap-4 text-2xl font-medium">
						<span
							class="h-2 w-2 rounded-full shadow-[0_0_12px_4px]"
							style="background-color:{siteGold}; --tw-shadow-color:{siteGold}"
						></span>
						work
					</span>
					<span class="text-sm text-muted">projects & experiments</span>
				</div>
				<span
					class="text-2xl transition-transform duration-300 group-hover:translate-x-1.5"
					style="color:{siteGold}">→</span
				>
			</div>
		</ElevatedCard>

		<ElevatedCard
			href="/writing"
			colors={[siteRed]}
			glowColor="8 95 55"
			class="group h-full w-full sm:w-72"
		>
			<div class="flex h-full items-center justify-between gap-6 p-8 text-left">
				<div class="flex flex-col gap-2 text-normal">
					<span class="flex items-center gap-4 text-2xl font-medium">
						<span
							class="h-2 w-2 rounded-full shadow-[0_0_12px_4px]"
							style="background-color:{siteRed}; --tw-shadow-color:{siteRed}"
						></span>
						writing
					</span>
					<span class="text-sm text-muted">essays & articles</span>
				</div>
				<span
					class="text-2xl transition-transform duration-300 group-hover:translate-x-1.5"
					style="color:{siteRed}">→</span
				>
			</div>
		</ElevatedCard>
	</section>
</main>
