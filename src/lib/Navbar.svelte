<script lang="ts">
	import logo from '$lib/assets/logo.png';
	import { page } from '$app/stores';
	let status = $page.url.pathname;
	let connected = false;
	let currentAddress = '0x';
	status = status;
</script>

<div class="">
	<nav class="w-screen">
		<ul class="flex items-end justify-between py-3 bg-transparent h1 pr-5">
			<li class="flex items-end ml-5 pb-2">
				<a href="/">
					<img src={logo} alt="" width={120} height={120} class="inline-block -mt-2" />
					<div class="inline-block font-bold text-xl ml-2">NFT Marketplace</div>
				</a>
			</li>
			<li class="w-2/6">
				<ul class="lg:flex justify-between font-bold mr-10 text-lg">
					{#if status === '/'}
						<li class="border-b2 hover:pb-0 p-2">
							<a href="/">Marketplace</a>
						</li>
					{:else}
						<li class="hover:border-b-2 hover:pb-0 pb-2">
							<a href="/">Marketplace</a>
						</li>
					{/if}
					{#if status === '/sellNFT'}
						<li class="border-b-2 hover:pb-0 p-2">
							<a href="/sellNFT">List My NFT</a>
						</li>
					{:else}
						<li class="hover:border-b-2 hover:pb-0 pb-2">
							<a href="/sellNFT">List My NFT</a>
						</li>
					{/if}
					{#if status === '/profile'}
						<li class="border-b-2 hover:pb-0 p-2">
							<a href="/profile">Profile</a>
						</li>
					{:else}
						<li class="hover:border-b-2 hover:pb-0 pb-2">
							<a href="/profile">Profile</a>
						</li>
					{/if}
					<li>
						<button class="btn font-bold py-2 px-4 rounded text-sm">
							{#if connected}
								Connected
							{:else}
								Connect Wallet
							{/if}
						</button>
					</li>
				</ul>
			</li>
		</ul>
	</nav>
	<div class="text-bold text-right mr-10 text-sm">
		{#if currentAddress !== '0x'}
			Connected To: {currentAddress.substring(0, 15) + '...'}
		{:else}
			Not Connected. Please login to view NFTs.
		{/if}
	</div>
</div>
