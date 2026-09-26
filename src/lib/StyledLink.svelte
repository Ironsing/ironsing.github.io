<script lang="ts">
	import type { Snippet } from 'svelte';
	import type { HTMLAnchorAttributes } from 'svelte/elements';

	type Props = HTMLAnchorAttributes & {
		children?: Snippet;
		href: string;
		class?: string;
	};

	let { children, href, class: className = '', ...rest }: Props = $props();
</script>

<a
	{href}
	class="text-site-gold underline decoration-site-gold/40 underline-offset-4 transition-colors duration-300 hover:decoration-site-gold {className}"
	{...rest}
>
	{@render children?.()}
</a>
