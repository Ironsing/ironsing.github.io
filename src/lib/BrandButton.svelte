<script lang="ts">
	type Props = {
		href: string;
		label: string;
		color: string;
		path: string;
	};

	let { href, label, color, path }: Props = $props();
</script>

<a
	{href}
	class="inline-flex items-center gap-3 rounded-lg px-4 py-2 font-medium text-white transition hover:brightness-110 active:brightness-95"
	style="background-color:{color}"
>
	<svg viewBox="0 0 24 24" class="h-6 w-6 fill-current" aria-hidden="true">
		<path d={path} />
	</svg>
	{label}
</a>
