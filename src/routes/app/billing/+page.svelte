<script lang="ts">
	import EmptyState from '$lib/components/ui/EmptyState.svelte';
	import PageHeader from '$lib/components/ui/PageHeader.svelte';
</script>

<PageHeader
	title="Billing"
	description="Billing placeholder for future subscription state, entitlement gates, and webhook-backed payment events."
/>

<EmptyState
	title="Billing foundation pending"
	description="Stripe integration, webhook verification, idempotency handling, and entitlement enforcement will be implemented in later phases."
	ctaLabel="Back to dashboard"
	ctaHref="/app"
/>
