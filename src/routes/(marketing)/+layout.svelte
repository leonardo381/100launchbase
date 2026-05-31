<script lang="ts">
	import { page } from '$app/state';
	import MarketingShell from '$lib/components/layout/MarketingShell.svelte';

	let { children } = $props();
</script>

<MarketingShell currentPath={page.url.pathname}>
	{@render children()}
</MarketingShell>
