<script>
	import Hero from '$lib/Hero.svelte';
	import StyledLink from '$lib/StyledLink.svelte';

	const essays = [
		{
			href: '/writing/entropy-intuitively',
			title: 'Entropy, intuitively'
		}
	];
</script>

<main class="flex w-full flex-1 flex-col items-center justify-center gap-12 px-6 py-20 lg:gap-16">
	<Hero class="max-w-3xl" ruleWidth="w-xs lg:w-3xl">
		{#snippet heading()}
			<div class="text-3xl lg:text-7xl">writing</div>
		{/snippet}
	</Hero>

	<ul class="flex w-full max-w-3xl flex-col items-center gap-10">
		{#each essays as essay (essay.href)}
			<li class="flex w-full justify-center">
				<StyledLink href={essay.href} class="text-lg font-medium">
					{essay.title}
				</StyledLink>
			</li>
		{/each}
	</ul>
</main>
