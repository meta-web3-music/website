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
		<div class="border-[#34343C] border-2 rounded-xl flex items-center">
			<input
				type="text"
				placeholder="E-mail"
				class="bg-transparent p-4 w-[80vw] md:w-[67vw] lg:w-[50vw] active:outline-none active:border-none focus:outline-none focus:border-none"
			/>
			<span class="text-2xl leading-3 mr-3">
				<iconify-icon icon="cil:arrow-right" />
			</span>
		</div>
		<div class="my-2" />
		<p class="ml-auto uppercase">Join the wailist For early access</p>
	</div>
</div>
