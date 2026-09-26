<script lang="ts">
	type Props = {
		class?: string;
	};

	let { class: className = '' }: Props = $props();
</script>

<div
	class="h-px w-3xl [background:linear-gradient(to_right,var(--color-site-red)_0_50%,var(--color-site-gold)_50%_100%)] {className}"
></div>
