<script lang="ts">
	import { siGithub, siProtonmail } from 'simple-icons';
	import BrandButton from '$lib/BrandButton.svelte';
	import Hero from '$lib/Hero.svelte';
	import StyledLink from '$lib/StyledLink.svelte';

	const links = {
		github: 'https://github.com/Ironsing',
		email: 'mailto:ironsing@proton.me'
	};
</script>

<main class="flex flex-1 flex-col items-center justify-center gap-16 px-6 py-20">
	<Hero title="about" class="max-w-3xl" />

	<div class="flex flex-col items-center justify-center gap-8">
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
			<p>The endgoal here is found startups, and to live a good life.</p>
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

		<StyledLink href="/">← back home</StyledLink>
	</div>
</main>
