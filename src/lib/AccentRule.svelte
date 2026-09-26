<script lang="ts">
	type Props = {
		/** Tailwind width utility for the rule. Defaults to `w-3xl`. */
		width?: string;
		class?: string;
	};

	let { width = 'w-3xl', class: className = '' }: Props = $props();
</script>

<div
	class="h-px {width} [background:linear-gradient(to_right,var(--color-site-red)_0_50%,var(--color-site-gold)_50%_100%)] {className}"
></div>
