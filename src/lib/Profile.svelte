<script lang="ts">
	import NftTile from './NFTTile.svelte';
	import Navbar from './Navbar.svelte';

	let data: Array<any> = [];
	let address: string = '0x';
	let totalPrice: string = '0';
</script>

<div class="min-h-screen">
	<Navbar />
	<div class="flex text-center flex-col mt-11 md:text-2xl">
		<div class="mb-5">
			<h2 class="font-bold">Wallet Adress</h2>
			{address}
		</div>
	</div>
	<div class="flex flex-row text-center justify-center mt-10 md:text-2xl">
		<div class="font-bold">
			<h2>No. of NFTs</h2>
			{data.length}
		</div>
		<div class="ml-20">
			<h2 class="font-bold">Total Price</h2>
			{totalPrice} ETH
		</div>
	</div>
	<div class="flex flex-col text-center items-center mt-11">
		<h2 class="font-bold">Your NFTs</h2>
		<div class="flex justify-center flex-wrap max-w-screen-xl">
			{#each data as item}
				<NftTile data={item} />
			{/each}
		</div>
		<div class="mt-10 text-xl">
			{#if data.length == 0}
				Oops, No NFT data to display (Are you logged in?)
			{/if}
		</div>
	</div>
</div>
