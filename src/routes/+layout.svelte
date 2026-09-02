<script lang="ts">
	import './layout.css';
	import Titlebar from '$lib/Titlebar.svelte';

	let {
		children
	}: {
		children: import('svelte').Snippet;
	} = $props();
</script>

<div class="flex min-h-screen w-screen flex-col bg-bg text-emphasis">
	<Titlebar />
	{@render children()}
	<footer class="w-full">
		<div class="flex items-center justify-center p-8 text-xs text-muted">
			<span>© {new Date().getFullYear()} ironsing.dev</span>
		</div>
	</footer>
</div>
