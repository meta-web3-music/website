<script>
	import { createClient } from '@supabase/supabase-js';
	import { PUBLIC_SUPABASE_URL, PUBLIC_SUPABASE_KEY } from '$env/static/public';
	export let form;
	let email = '';

	let waitlist_added = false;
	let already_exist = false;

	const supabaseUrl = PUBLIC_SUPABASE_URL;
	const supabaseKey = PUBLIC_SUPABASE_KEY;
	const supabase = createClient(supabaseUrl, supabaseKey);
	// Make a request

	const run = async () => {
		if (email == '' || !email) {
			alert('email is required');
			return;
		}
		const { error } = await supabase.from('mails').insert({ email_id: email });
		if (!!error && error?.code == '23505') {
			already_exist = true;
			console.log('email already exist');
			setTimeout(() => {
				already_exist = false;
			}, 2500);
			return;
		}
		waitlist_added = true;
		setTimeout(() => {
			waitlist_added = false;
		}, 5000);
		console.log('inserted');
	};
</script>

<header
	class="flex px-5 py-4 items-center fixed w-full font-figtree bg-[#F7F7F7] dark:bg-[#121212]"
>
	<img src="/images/OCTAV3_logo.png" />
	<div class="mx-1" />
	<h2 class="text-2xl font-bold dark:text-white">OCTAV3</h2>

	<div class="flex fixed bottom-8 right-8">
		<button
			class="bg-[#F3EA01] pl-4 py-2 rounded-3xl font-semibold flex items-center"
			on:click={() => (window.location.href = 'https://app.octav3.com')}
		>
			Visit Classic OCTAV3
			<span class="text-3xl my-auto leading-6">
				<iconify-icon icon="mdi-light:chevron-right" />
			</span>
		</button>
	</div>
</header>
<div
	class="landing-container h-full flex items-center justify-center flex-col font-figtree bg-[#F7F7F7] dark:bg-[#121212]"
>
	<div class="inline-flex flex-col text-center font-bold text-7xl dark:text-white">
		<p>Stay In Touch With Your Favourite</p>
		<p>Artists & Music Community</p>
	</div>

	<p class="mx-20 lg:mx-60 mt-1 text-center text-xl text-[rgba(255,255,255,0.56)]">
		OCTAV3 unites artists and fans. Stream, Connect, and Collect music like never before!
	</p>
	<div class="my-4" />
	<div class="text-white flex flex-col">
		<form class="border-[#34343C] border-2 rounded-xl flex items-center" on:submit={run}>
			{#if form?.error}
				<p class="error">{form.error}</p>
			{/if}
			<input
				required
				type="email"
				placeholder="E-mail"
				bind:value={email}
				class="bg-transparent p-4 w-[80vw] md:w-[67vw] lg:w-[50vw] active:outline-none active:border-none focus:outline-none focus:border-none"
			/>
			<button class="text-2xl leading-3 mr-3">
				<iconify-icon icon="cil:arrow-right" />
			</button>
		</form>
		<div class="my-2" />
		<p class="ml-auto uppercase">
			{#if already_exist}
				Email already exist
			{:else}
				{waitlist_added ? 'Wailist joined' : 'Join the wailist For early access'}
			{/if}
		</p>
	</div>
</div>
