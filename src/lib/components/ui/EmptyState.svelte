<script lang="ts">
	import { resolve } from '$app/paths';

	let { ctaHref = '#', ctaLabel, description, title } = $props<{
		ctaHref?: string;
		ctaLabel?: string;
		description: string;
		title: string;
	}>();
</script>

<div class="rounded-xl border border-slate-200 bg-white p-8 shadow-sm">
	<div class="mx-auto max-w-2xl text-center">
		<h2 class="text-xl font-semibold text-slate-900">{title}</h2>
		<p class="mt-3 text-sm text-slate-600">{description}</p>

		{#if ctaLabel}
			<a
				href={resolve(ctaHref)}
				class="mt-5 inline-flex items-center rounded-lg border border-slate-300 px-4 py-2 text-sm font-medium text-slate-700 transition hover:bg-slate-100"
			>
				{ctaLabel}
			</a>
		{/if}
	</div>
</div>
