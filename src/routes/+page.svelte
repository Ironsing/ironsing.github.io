<script lang="ts">
	import BrandButton from '$lib/BrandButton.svelte';
	import ElevatedCard from '$lib/ElevatedCard.svelte';
	import Hero from '$lib/Hero.svelte';
	import { siGithub, siProtonmail } from 'simple-icons';
	import { siteRed, siteGold } from '$lib/design-tokens';

	const links = {
		github: 'https://github.com/Ironsing',
		email: 'mailto:ironsing@proton.me'
	};
</script>

<main
	class="flex h-full w-full flex-1 flex-col items-center justify-center gap-10 px-6 py-20 lg:gap-10"
>
	<Hero ruleWidth="w-xs lg:w-3xl">
		{#snippet heading()}
			<div class="text-3xl lg:text-7xl">
				hey, i’m <span class="text-site-gold">Aayush Digikar.</span>
			</div>
		{/snippet}
	</Hero>

	<div class="flex flex-col items-center justify-center gap-8 lowercase">
		<div
			class="flex max-w-xl flex-col items-center gap-6 text-center text-sm text-normal lg:text-lg"
		>
			<p>
				i'm a programmer, occasional writer, and first-year college student from India. i also go by <code
					>ironsing</code
				> online. i have exactly four goals:
			</p>
			<ol class="list-decimal pl-6 text-left lg:pl-8">
				<li>hoard things I know how to do,</li>
				<li>produce public evidence of work,</li>
				<li>tell people about that work,</li>
				<li>and, in general, build things.</li>
			</ol>
		</div>
	</div>

	<section
		class="flex w-full flex-col items-center justify-center gap-6 text-center text-sm text-normal lg:text-lg"
	>
		<div>here's my stuff:</div>
		<div class="flex flex-wrap items-center justify-center gap-4">
			<BrandButton
				href={links.github}
				label={siGithub.title}
				color="#30363d"
				path={siGithub.path}
			/>
			<BrandButton
				href={links.email}
				label={siProtonmail.title}
				color={`#${siProtonmail.hex}`}
				path={siProtonmail.path}
			/>
		</div>
		<div class=" flex flex-col items-center justify-center gap-6 lg:flex-row">
			<ElevatedCard
				href="/work"
				colors={[siteGold]}
				glowColor="45 90 60"
				class="group h-full w-full max-w-72 lg:w-72"
			>
				<div class="flex h-full items-center justify-between gap-6 p-8 text-left">
					<div class="flex flex-col gap-2 text-emphasis">
						<span class="flex items-center gap-4 text-lg font-medium lg:text-2xl">
							<span
								class="h-2 w-2 rounded-full shadow-[0_0_12px_4px]"
								style="background-color:{siteGold}; --tw-shadow-color:{siteGold}"
							></span>
							work
						</span>
						<span class="text-sm text-muted">mostly software stuff</span>
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
				class="group h-full w-full max-w-72 lg:w-72"
			>
				<div class="flex h-full items-center justify-between gap-6 p-8 text-left">
					<div class="flex flex-col gap-2 text-emphasis">
						<span class="flex items-center gap-4 text-lg font-medium lg:text-2xl">
							<span
								class="h-2 w-2 rounded-full shadow-[0_0_12px_4px]"
								style="background-color:{siteRed}; --tw-shadow-color:{siteRed}"
							></span>
							writing
						</span>
						<span class="text-sm text-muted">essays & whatnot</span>
					</div>
					<span
						class="text-2xl transition-transform duration-300 group-hover:translate-x-1.5"
						style="color:{siteRed}">→</span
					>
				</div>
			</ElevatedCard>
		</div>
	</section>
</main>
