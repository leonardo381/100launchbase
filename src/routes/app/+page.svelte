<script lang="ts">
	import EmptyState from '$lib/components/ui/EmptyState.svelte';
	import PageHeader from '$lib/components/ui/PageHeader.svelte';
</script>

<PageHeader
	title="Dashboard"
	description="Dashboard surface for future SaaS Core modules. This page currently contains placeholder UI only."
/>

<EmptyState
	title="Dashboard module coming next"
	description="Use this area for tenant-scoped operational metrics once server-side SaaS Core services are connected. No runtime business data is implemented in this phase."
	ctaLabel="View settings"
	ctaHref="/app/settings"
/>
