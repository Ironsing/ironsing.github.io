<script lang="ts">
	import './layout.css';
	import '@fontsource-variable/google-sans-flex';
	import Titlebar from '$lib/Titlebar.svelte';

	let {
		children
	}: {
		children: import('svelte').Snippet;
	} = $props();
</script>

<div class="flex h-dvh min-h-dvh w-dvw flex-col overflow-x-hidden bg-bg">
	<Titlebar />
	{@render children()}
	<footer class="w-full">
		<div class="flex items-center justify-center p-8 text-xs text-muted">
			<span>© {new Date().getFullYear()} ironsing.dev</span>
		</div>
	</footer>
</div>
