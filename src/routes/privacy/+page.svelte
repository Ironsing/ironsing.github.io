<script lang="ts">
	import Hero from '$lib/Hero.svelte';
</script>

<main class="flex flex-1 flex-col items-center justify-center gap-10 px-6 py-20 lg:gap-16">
	<Hero ruleWidth="w-xs lg:w-3xl">
		{#snippet heading()}
			<div class="text-3xl lg:text-7xl">privacy</div>
		{/snippet}
	</Hero>

	<div class="max-w-xl text-sm leading-7 text-normal lg:text-lg">
		<p>
			This site uses Google Analytics to understand aggregate traffic and how visitors use the site.
			Google Analytics may collect information such as pages viewed, approximate geographic
			location, device/browser information, and identifiers associated with your visit. Analytics
			data is sent to Google and is used to provide measurement and reporting. This site does not
			intentionally send personally identifiable information to Google Analytics.
		</p>
	</div>
</main>
