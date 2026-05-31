<script lang="ts">
	import { resolve } from '$app/paths';
	import type { Snippet } from 'svelte';

	let { children } = $props<{ children?: Snippet }>();
</script>

<div class="min-h-screen bg-slate-100 px-4 py-10">
	<div class="mx-auto flex min-h-screen w-full max-w-md flex-col justify-center">
		<a
			href={resolve('/')}
			class="mb-6 inline-flex items-center gap-2 self-center text-sm font-semibold text-slate-700"
		>
			<span
				class="flex h-8 w-8 items-center justify-center rounded-md bg-slate-900 text-xs font-semibold text-white"
			>
				LB
			</span>
			LaunchBase
		</a>

		<div class="rounded-xl border border-slate-200 bg-white p-6 shadow-sm sm:p-8">
			{@render children?.()}
		</div>
	</div>
</div>
