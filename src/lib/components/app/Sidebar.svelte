<script lang="ts">
	import { resolve } from '$app/paths';

	type AppNavHref = '/app' | '/app/settings' | '/app/team' | '/app/billing';

	type AppNavItem = {
		description: string;
		href: AppNavHref;
		label: string;
	};

	let { currentPath = '/app' } = $props<{ currentPath?: string }>();

	const navItems: AppNavItem[] = [
		{
			description: 'Overview and progress',
			href: '/app',
			label: 'Dashboard'
		},
		{
			description: 'Workspace configuration',
			href: '/app/settings',
			label: 'Settings'
		},
		{
			description: 'Team membership placeholder',
			href: '/app/team',
			label: 'Team'
		},
		{
			description: 'Subscription and usage placeholder',
			href: '/app/billing',
			label: 'Billing'
		}
	];

	const isActive = (href: AppNavHref): boolean =>
		currentPath === href || (href !== '/app' && currentPath.startsWith(`${href}/`));
</script>

<div class="flex h-full flex-col">
	<div class="border-b border-slate-200 px-5 py-4">
		<a href={resolve('/app')} class="inline-flex items-center gap-2 text-sm font-semibold text-slate-900">
			<span
				class="flex h-8 w-8 items-center justify-center rounded-md bg-slate-900 text-xs font-semibold text-white"
			>
				LB
			</span>
			LaunchBase
		</a>
		<p class="mt-2 text-xs text-slate-500">SaaS Core foundation</p>
	</div>

	<nav class="flex-1 space-y-2 p-4">
		{#each navItems as item (item.href)}
			<a
				href={resolve(item.href)}
				class={`block rounded-lg border px-3 py-3 transition ${
					isActive(item.href)
						? 'border-slate-300 bg-slate-100 text-slate-900'
						: 'border-transparent text-slate-600 hover:border-slate-200 hover:bg-slate-50 hover:text-slate-900'
				}`}
				aria-current={isActive(item.href) ? 'page' : undefined}
			>
				<p class="text-sm font-medium">{item.label}</p>
				<p class="mt-1 text-xs text-slate-500">{item.description}</p>
			</a>
		{/each}
	</nav>

	<div class="border-t border-slate-200 p-4">
		<p class="text-xs uppercase tracking-wide text-slate-500">Workspace</p>
		<p class="mt-1 text-sm font-medium text-slate-800">Acme Workspace</p>
		<p class="mt-1 text-xs text-slate-500">UI placeholder only</p>
	</div>
</div>
