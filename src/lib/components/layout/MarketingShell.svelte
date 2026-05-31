<script lang="ts">
	import { resolve } from '$app/paths';
	import type { Snippet } from 'svelte';

	type NavHref = '/pricing' | '/login' | '/signup';

	type NavItem = {
		href: NavHref;
		label: string;
	};

	let { children, currentPath = '/' } = $props<{
		children?: Snippet;
		currentPath?: string;
	}>();

	const navItems: NavItem[] = [
		{ href: '/pricing', label: 'Pricing' },
		{ href: '/login', label: 'Login' },
		{ href: '/signup', label: 'Sign up' }
	];

	const isActive = (href: NavHref): boolean => currentPath === href;
</script>

<div class="min-h-screen bg-slate-50 text-slate-900">
	<header class="border-b border-slate-200 bg-white/95 backdrop-blur">
		<div class="mx-auto flex h-16 w-full max-w-6xl items-center justify-between px-4 sm:px-6 lg:px-8">
			<a href={resolve('/')} class="inline-flex items-center gap-2 text-sm font-semibold text-slate-900">
				<span
					class="flex h-8 w-8 items-center justify-center rounded-md bg-slate-900 text-xs font-semibold text-white"
				>
					LB
				</span>
				LaunchBase
			</a>

			<nav class="flex items-center gap-2 sm:gap-3">
				{#each navItems as item (item.href)}
					<a
						href={resolve(item.href)}
						class={`rounded-lg px-3 py-2 text-sm font-medium transition ${
							isActive(item.href)
								? 'bg-slate-100 text-slate-900'
								: 'text-slate-600 hover:bg-slate-100 hover:text-slate-900'
						}`}
						aria-current={isActive(item.href) ? 'page' : undefined}
					>
						{item.label}
					</a>
				{/each}
			</nav>
		</div>
	</header>

	<main class="mx-auto w-full max-w-6xl px-4 py-12 sm:px-6 lg:px-8">
		{@render children?.()}
	</main>
</div>
