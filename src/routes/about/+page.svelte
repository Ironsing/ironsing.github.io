<script lang="ts">
	import { siGithub, siProtonmail } from 'simple-icons';
	import BrandButton from '$lib/BrandButton.svelte';

	const links = {
		github: 'https://github.com/Ironsing',
		email: 'mailto:ironsing@proton.me'
	};
</script>

<main class="flex flex-1 flex-col items-center justify-center gap-20 px-6 py-20">
	<section class="flex max-w-3xl flex-col items-center gap-6 text-center">
		<h1 class="max-w-3xl font-serif text-4xl leading-tight font-medium text-emphasis sm:text-7xl">
			about
		</h1>
		<div
			class="h-px w-48 [background:linear-gradient(to_right,var(--color-site-red)_0_50%,var(--color-site-gold)_50%_100%)] sm:w-3xl"
		></div>

		<div class="flex max-w-xl flex-col items-center gap-6 text-lg text-normal">
			<p>
				I'm Aayush Digikar, a programmer and first-year college student from India. I also go by <code
					>ironsing</code
				> online. I have exactly three goals:
			</p>
			<ol class="list-decimal pl-8 text-left">
				<li>hoard things I know how to do,</li>
				<li>produce public evidence of work,</li>
				<li>and build things.</li>
			</ol>
			<p>
				The endgoal here is found startups, and to live a good life.
			</p>
		</div>

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
	</section>

	<a
		href="/"
		class="text-site-gold underline decoration-site-gold/40 underline-offset-4 transition-colors duration-300 hover:decoration-site-gold"
		>← back home</a
	>
</main>
