<script lang="ts">
	import EmptyState from '$lib/components/ui/EmptyState.svelte';
	import PageHeader from '$lib/components/ui/PageHeader.svelte';
</script>

<PageHeader
	title="Settings"
	description="Settings placeholders for future organization-level and workspace-facing configuration surfaces."
/>

<EmptyState
	title="Settings module placeholder"
	description="Future secure settings workflows will rely on server-side authorization and tenant-scoped configuration using organizationId ownership."
	ctaLabel="Go to team"
	ctaHref="/app/team"
/>
