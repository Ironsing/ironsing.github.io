<script lang="ts">
	import type { Snippet } from 'svelte';
	import BorderGlow from '$lib/BorderGlow.svelte';
	import { bg } from '$lib/design-tokens';

	type Props = {
		/** Render as a link when provided, otherwise a non-interactive surface. */
		href?: string;
		/** Corner radius in px, shared by the surface and its glow. */
		borderRadius?: number;
		/** Opts into the BorderGlow layer. HSL string, e.g. "45 90 60". */
		glowColor?: string;
		/** Colors fed to the glow mesh. */
		colors?: string[];
		class?: string;
		children?: Snippet;
	};

	let {
		href,
		borderRadius = 18,
		glowColor,
		colors,
		class: className = '',
		children
	}: Props = $props();

	// BorderGlow already paints its own stacked elevation, so only add our own
	// shadow when no glow layer is present, to avoid doubling the lift.
	// Sizing is deliberately left to the caller: base `w-full`/`h-full` utilities
	// would win the stylesheet-order tiebreak against caller values like `w-80`,
	// and would force equal heights on cards that should size to their content.
	const shapeClass = $derived(
		[
			'block border border-white/15 bg-bg',
			glowColor ? '' : 'shadow-[0_6px_16px_-6px_rgba(0,0,0,0.55)]',
			className
		]
			.filter(Boolean)
			.join(' ')
	);
</script>

{#snippet surface()}
	{#if glowColor}
		<BorderGlow {glowColor} {colors} backgroundColor={bg} {borderRadius} class="h-full w-full">
			{@render children?.()}
		</BorderGlow>
	{:else}
		{@render children?.()}
	{/if}
{/snippet}

{#if href}
	<a {href} class={shapeClass} style="border-radius:{borderRadius}px">
		{@render surface()}
	</a>
{:else}
	<div class={shapeClass} style="border-radius:{borderRadius}px">
		{@render surface()}
	</div>
{/if}
