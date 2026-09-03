<script lang="ts">
	import BorderGlow from '$lib/BorderGlow.svelte';
	import { siteRed, siteGold, bg } from '$lib/design-tokens';
</script>

<main class="flex w-full flex-1 flex-col items-center justify-center gap-20 px-6 py-20">
	<section class="flex flex-col items-center gap-6 text-center">
		<h1 class="max-w-3xl font-serif text-6xl leading-tight font-medium text-emphasis">
			hey, i’m <a
				href="/about"
				class="text-site-gold underline decoration-site-gold/40 underline-offset-4 transition-colors duration-300 hover:decoration-site-gold"
				>Aayush Digikar.</a
			>
		</h1>
		<p class="max-w-xl text-lg text-normal">
			i like doing things. feel free to take a gander below.
		</p>
		<div
			class="h-px w-3xl [background:linear-gradient(to_right,var(--color-site-red)_0_50%,var(--color-site-gold)_50%_100%)]"
		></div>
	</section>

	<section class="flex w-full max-w-3xl flex-row items-stretch justify-center gap-6">
		<a href="/work" class="group w-full sm:w-72">
			<BorderGlow
				colors={[siteGold]}
				backgroundColor={bg}
				borderRadius={18}
				glowColor="45 90 60"
				class="h-full w-full"
			>
				<div class="flex h-full items-center justify-between gap-6 p-8 text-left">
					<div class="flex flex-col gap-2">
						<span class="flex items-center gap-3 text-2xl font-medium">
							<span
								class="h-2 w-2 rounded-full bg-site-gold shadow-[0_0_12px_4px] shadow-site-gold/55"
							></span>
							work
						</span>
						<span class="text-sm text-normal">projects & experiments</span>
					</div>
					<span
						class="text-2xl text-site-gold transition-transform duration-300 group-hover:translate-x-1.5"
						>→</span
					>
				</div>
			</BorderGlow>
		</a>

		<a href="/writing" class="group w-full sm:w-72">
			<BorderGlow
				colors={[siteRed]}
				backgroundColor={bg}
				borderRadius={18}
				glowColor="8 95 55"
				class="h-full w-full"
			>
				<div class="flex h-full items-center justify-between gap-6 p-8 text-left">
					<div class="flex flex-col gap-2">
						<span class="flex items-center gap-3 text-2xl leading-none font-medium">
							<span
								class="h-2 w-2 rounded-full bg-site-red shadow-[0_0_12px_4px] shadow-site-red/55"
							></span>
							writing
						</span>
						<span class="text-sm text-normal">essays & articles</span>
					</div>
					<span
						class="text-2xl text-site-red transition-transform duration-300 group-hover:translate-x-1.5"
						>→</span
					>
				</div>
			</BorderGlow>
		</a>
	</section>
</main>
