<script>
		import DarkModeToggle from '../components/DarkModeToggle.svelte'
</script>
<header class="flex px-5 py-4 items-center fixed w-full font-figtree bg-[#F7F7F7] dark:bg-[#121212]">
	<h2 class="text-2xl font-bold dark:text-white">OCTAV3</h2>
	<nav class="mx-auto flex text-[rgb(0,0,0,0.7)] dark:text-white">
		<a href="https://octav3.gitbook.io/octav3/" target="_blank" rel="noopener noreferrer"
			><h2 class="mr-4 hover:underline">Docs</h2></a
		>
		<a href="https://octav3.substack.com/" target="_blank" rel="noopener noreferrer">
			<h2 class="mr-4 hover:underline">Blog</h2></a
		>
	</nav>
	<div class="flex">
		<DarkModeToggle></DarkModeToggle>
		<button class="bg-[#F3EA01] px-8 py-2 rounded-lg font-bold" on:click={()=>window.location.href="https://app.octav3.com"}>
			Go to app
		</button>
	</div>

</header>
<div
	class="landing-container h-full flex items-center justify-center flex-col font-figtree bg-[#F7F7F7] dark:bg-[#121212]"
>
	<div class="inline-flex flex-col text-center font-bold text-7xl dark:text-white">
	<p>Make Money From Your</p>
	<p> Music NFTs</p>
	</div>
	<p class="mx-20 lg:mx-60 mt-1 text-center text-xl text-[rgb(0,0,0,0.56)] dark:text-white">
		OCTAV3 is a web3 music streaming platform that connects artists, listeners and advertisers.
	</p>

	<div class="flex text-[#BFB00D] mt-14 absolute bottom-40 text-2xl">
		<!-- TODO: Add target="_blank" rel="noopener noreferrer" -->
		<a href="/"> <iconify-icon icon="bi:discord" class="mr-6" /></a>

		<a href="https://twitter.com/octav3_music" target="_blank" rel="noopener noreferrer">
			<iconify-icon icon="bi:twitter" /></a
		>
	</div>
</div>

