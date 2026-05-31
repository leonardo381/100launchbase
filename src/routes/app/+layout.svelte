<script lang="ts">
	import { page } from '$app/state';
	import AppShell from '$lib/components/layout/AppShell.svelte';

	let { children } = $props();
</script>

<AppShell currentPath={page.url.pathname}>
	{@render children()}
</AppShell>
