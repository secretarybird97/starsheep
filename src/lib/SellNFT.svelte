<script lang="ts">
	import Navbar from '$lib/Navbar.svelte';

	let formParams = { name: '', description: '', price: '' };
	let fileURL = null;
	// let ethers = require('ethers');
	let message = '';
	let location;
</script>

<div>
	<Navbar />
	<div class="flex flex-col place-items-center mt-10" id="nftForm">
		<form class="bg-white shadow-md rounded px-8 pt-4 pb-8 mb-4">
			<h3 class="text-center font-bold mb-8">Uppload your NFT to the marketplace</h3>
			<div class="mb-4">
				<label class="block text-sm font-bold mb-2" for="name">NFT Name</label>
				<input
					class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
					id="name"
					type="text"
					placeholder="Axie #4563"
					bind:value={formParams.name}
				/>
			</div>
			<div class="mb-6">
				<label class="block text-sm font-bold mb-2" for="description">NFT Description</label>
				<textarea
					class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
					id="description"
					placeholder="Axie Infinity Collection"
					bind:value={formParams.description}
				/>
			</div>
			<div>
				<label class="block text-sm font-bold mb-2" for="price">Price (in ETH)</label>
				<input
					class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
					type="number"
					placeholder="Min 0.01 ETH"
					step="0.01"
					bind:value={formParams.price}
				/>
			</div>
			<div>
				<label class="block text-sm font-bold mb-2" for="price">Upload Image (&lt;500 KB)</label>
				<input type="file" />
			</div>
			<br />
			<div class="text-center">{message}</div>
			<button class="btn font-bold p-2 shadow-lg" id="list-button">List NFT</button>
		</form>
	</div>
</div>
