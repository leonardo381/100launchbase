<script lang="ts">
	import AuthShell from '$lib/components/layout/AuthShell.svelte';

	let { children } = $props();
</script>

<AuthShell>
	{@render children()}
</AuthShell>
