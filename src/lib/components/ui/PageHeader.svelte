<script lang="ts">
	import type { Snippet } from 'svelte';

	let { title, description, actions } = $props<{
		actions?: Snippet;
		description?: string;
		title: string;
	}>();
</script>

<div class="mb-6 flex flex-col gap-4 border-b border-slate-200 pb-5 sm:flex-row sm:items-start sm:justify-between">
	<div class="space-y-1">
		<h1 class="text-2xl font-semibold tracking-tight text-slate-900">{title}</h1>
		{#if description}
			<p class="text-sm text-slate-600">{description}</p>
		{/if}
	</div>

	{#if actions}
		<div class="shrink-0">
			{@render actions()}
		</div>
	{/if}
</div>
