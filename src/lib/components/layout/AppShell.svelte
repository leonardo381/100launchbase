<script lang="ts">
	import type { Snippet } from 'svelte';
	import Sidebar from '$lib/components/app/Sidebar.svelte';
	import Topbar from '$lib/components/app/Topbar.svelte';

	let { children, currentPath = '/app' } = $props<{
		children?: Snippet;
		currentPath?: string;
	}>();
</script>

<div class="min-h-screen bg-slate-50 text-slate-900">
	<div class="mx-auto flex min-h-screen w-full max-w-[1600px]">
		<aside class="hidden w-72 border-r border-slate-200 bg-white lg:block">
			<Sidebar {currentPath} />
		</aside>

		<div class="flex min-h-screen min-w-0 flex-1 flex-col">
			<Topbar />

			<main class="flex-1 p-4 sm:p-6 lg:p-8">
				<div class="mx-auto w-full max-w-6xl">
					<div class="mb-4 rounded-lg border border-dashed border-slate-300 bg-slate-100 px-3 py-2 text-xs text-slate-600 lg:hidden">
						Sidebar navigation is optimized for desktop and appears on larger screens.
					</div>
					{@render children?.()}
				</div>
			</main>
		</div>
	</div>
</div>
