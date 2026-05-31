<script lang="ts">
	import { resolve } from '$app/paths';

	const handlePlaceholderSubmit = (event: SubmitEvent): void => {
		event.preventDefault();
	};
</script>

<h1 class="text-2xl font-semibold tracking-tight text-slate-900">Sign in to LaunchBase</h1>
<p class="mt-2 text-sm text-slate-600">UI placeholder only. Authentication will be implemented in a later phase.</p>

<form class="mt-6 space-y-5" onsubmit={handlePlaceholderSubmit}>
	<div>
		<label class="mb-2 block text-sm font-medium text-slate-700" for="email">Work email</label>
		<input
			id="email"
			name="email"
			type="email"
			required
			class="block w-full rounded-lg border border-slate-300 bg-white px-3 py-2.5 text-sm text-slate-900 shadow-sm focus:border-slate-400 focus:outline-none"
			placeholder="you@company.com"
		/>
	</div>

	<div>
		<label class="mb-2 block text-sm font-medium text-slate-700" for="password">Password</label>
		<input
			id="password"
			name="password"
			type="password"
			required
			class="block w-full rounded-lg border border-slate-300 bg-white px-3 py-2.5 text-sm text-slate-900 shadow-sm focus:border-slate-400 focus:outline-none"
			placeholder="••••••••"
		/>
	</div>

	<div class="flex items-center justify-between">
		<label class="inline-flex items-center gap-2 text-sm text-slate-600" for="remember">
			<input id="remember" name="remember" type="checkbox" class="rounded border-slate-300" />
			Remember this device
		</label>
		<button type="button" class="text-sm font-medium text-slate-700 transition hover:text-slate-900">
			Forgot password?
		</button>
	</div>

	<button
		type="submit"
		class="w-full rounded-lg bg-slate-900 px-4 py-2.5 text-sm font-medium text-white transition hover:bg-slate-800"
	>
		Sign in
	</button>
</form>

<p class="mt-6 text-center text-sm text-slate-600">
	Need an account?
	<a href={resolve('/signup')} class="font-medium text-slate-900 hover:underline">Create one</a>
</p>
