<script lang="ts">
	import EmptyState from '$lib/components/ui/EmptyState.svelte';
	import PageHeader from '$lib/components/ui/PageHeader.svelte';
</script>

<PageHeader
	title="Team"
	description="Team and role management placeholder for future server-side RBAC and invite flows."
/>

<EmptyState
	title="Team management coming soon"
	description="This section is reserved for secure member lifecycle flows such as invites, role assignments, and audit-tracked changes."
	ctaLabel="Go to billing"
	ctaHref="/app/billing"
/>
