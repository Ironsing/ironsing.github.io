<script lang="ts">
	import type { Snippet } from 'svelte';
	import AccentRule from '$lib/AccentRule.svelte';

	type Props = {
		/** Plain-text heading. Use `heading` instead for rich content. */
		title?: string;
		/** Rich heading content; takes precedence over `title`. */
		heading?: Snippet;
		/** Optional subtitle rendered between the heading and the rule. */
		lead?: Snippet;
		class?: string;
	};

	let { title, heading, lead, class: className = '' }: Props = $props();

	const headingClass =
		'max-w-3xl font-serif text-6xl leading-tight font-medium text-emphasis sm:text-7xl';
</script>

<section class="flex flex-col items-center gap-6 text-center {className}">
	<h1 class={headingClass}>
		{#if heading}
			{@render heading()}
		{:else}
			{title}
		{/if}
	</h1>
	{#if lead}
		{@render lead()}
	{/if}
	<AccentRule />
</section>
