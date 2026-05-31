<script lang="ts">
	import { resolve } from '$app/paths';

	const handlePlaceholderSubmit = (event: SubmitEvent): void => {
		event.preventDefault();
	};
</script>

<h1 class="text-2xl font-semibold tracking-tight text-slate-900">Create your LaunchBase account</h1>
<p class="mt-2 text-sm text-slate-600">UI placeholder only. Account creation flow will be implemented later.</p>

<form class="mt-6 space-y-5" onsubmit={handlePlaceholderSubmit}>
	<div>
		<label class="mb-2 block text-sm font-medium text-slate-700" for="fullName">Full name</label>
		<input
			id="fullName"
			name="fullName"
			type="text"
			required
			class="block w-full rounded-lg border border-slate-300 bg-white px-3 py-2.5 text-sm text-slate-900 shadow-sm focus:border-slate-400 focus:outline-none"
			placeholder="Jane Doe"
		/>
	</div>

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
			placeholder="Minimum 8 characters"
		/>
	</div>

	<label class="inline-flex items-center gap-2 text-sm text-slate-600" for="terms">
		<input id="terms" name="terms" type="checkbox" required class="rounded border-slate-300" />
		I agree to the terms and privacy notice.
	</label>

	<button
		type="submit"
		class="w-full rounded-lg bg-slate-900 px-4 py-2.5 text-sm font-medium text-white transition hover:bg-slate-800"
	>
		Create account
	</button>
</form>

<p class="mt-6 text-center text-sm text-slate-600">
	Already have an account?
	<a href={resolve('/login')} class="font-medium text-slate-900 hover:underline">Sign in</a>
</p>
