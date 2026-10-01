<script lang="ts">
	import katex from 'katex';

	type Props = {
		/** LaTeX source, without delimiters. */
		tex: string;
		/** Block (display) mode for standalone equations; inline otherwise. */
		display?: boolean;
		class?: string;
	};

	let { tex, display = true, class: className = '' }: Props = $props();

	// Rendered during SSR so the static HTML already contains the typeset math.
	// `throwOnError: false` keeps a typo in the source from failing the build.
	// Default output is 'htmlAndMathml', which also emits the MathML that
	// screen readers rely on, so it is deliberately left unset.
	const html = $derived(katex.renderToString(tex, { displayMode: display, throwOnError: false }));
</script>

{#if display}
	<!-- Block, not flex: KaTeX positions `\tag{n}` absolutely against
	     the katex-display box, which a flex item would shrink-wrap. -->
	<div class="overflow-x-auto text-center {className}">
		{@html html}
	</div>
{:else}
	<span class={className}>{@html html}</span>
{/if}
