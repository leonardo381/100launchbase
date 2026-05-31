<script lang="ts">
	import { resolve } from '$app/paths';
</script>

<section class="rounded-2xl border border-slate-200 bg-white p-8 shadow-sm sm:p-10">
	<p class="text-sm font-medium uppercase tracking-wide text-slate-500">SaaS technical foundation</p>
	<h1 class="mt-4 max-w-3xl text-3xl font-semibold tracking-tight text-slate-900 sm:text-4xl">
		LaunchBase gives teams a clean, secure-first starting point for modern multi-tenant SaaS products.
	</h1>
	<p class="mt-4 max-w-2xl text-base text-slate-600">
		Phase 1 focuses on app shell and route foundation only. Product modules, authentication, billing, and data
		services are intentionally deferred to upcoming SaaS Core phases.
	</p>
	<div class="mt-8 flex flex-wrap gap-3">
		<a
			href={resolve('/signup')}
			class="inline-flex items-center rounded-lg bg-slate-900 px-4 py-2.5 text-sm font-medium text-white transition hover:bg-slate-800"
		>
			Create account
		</a>
		<a
			href={resolve('/login')}
			class="inline-flex items-center rounded-lg border border-slate-300 px-4 py-2.5 text-sm font-medium text-slate-700 transition hover:bg-slate-100"
		>
			Sign in
		</a>
	</div>
</section>

<section class="mt-8 grid gap-4 md:grid-cols-3">
	<article class="rounded-xl border border-slate-200 bg-white p-5 shadow-sm">
		<h2 class="text-base font-semibold text-slate-900">Security-first baseline</h2>
		<p class="mt-2 text-sm text-slate-600">
			Architecture choices in this project prioritize future auth, tenant isolation, RBAC, billing gates, and
			auditability.
		</p>
	</article>

	<article class="rounded-xl border border-slate-200 bg-white p-5 shadow-sm">
		<h2 class="text-base font-semibold text-slate-900">SaaS Core ready</h2>
		<p class="mt-2 text-sm text-slate-600">
			Public, auth, and app route groups are separated to keep future server-side authorization and module
			boundaries maintainable.
		</p>
	</article>

	<article class="rounded-xl border border-slate-200 bg-white p-5 shadow-sm">
		<h2 class="text-base font-semibold text-slate-900">Flowbite-aligned UI</h2>
		<p class="mt-2 text-sm text-slate-600">
			The visual foundation follows clean B2B SaaS patterns inspired by Flowbite and Flowbite Pro.
		</p>
	</article>
</section>
