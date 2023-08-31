<script lang="ts">
	import Navbar from './Navbar.svelte';
	import NFTTile from './NFTTile.svelte';
	import { GetIpfsUrlFromPinata } from '$lib/utils';

	const sampleData = [
		{
			name: 'NFT#1',
			description: "Alchemy's First NFT",
			website: 'http://axieinfinity.io',
			image: 'https://gateway.pinata.cloud/ipfs/QmTsRJX7r5gyubjkdmzFrKQhHv74p5wT9LdeF1m3RTqrE5',
			price: '0.03ETH',
			currentlySelling: 'True',
			address: '0xe81Bf5A757CB4f7F82a2F23b1e59bE45c33c5b13'
		},
		{
			name: 'NFT#2',
			description: "Alchemy's Second NFT",
			website: 'http://axieinfinity.io',
			image: 'https://gateway.pinata.cloud/ipfs/QmdhoL9K8my2vi3fej97foiqGmJ389SMs55oC5EdkrxF2M',
			price: '0.03ETH',
			currentlySelling: 'True',
			address: '0xe81Bf5A757C4f7F82a2F23b1e59bE45c33c5b13'
		},
		{
			name: 'NFT#3',
			description: "Alchemy's Third NFT",
			website: 'http://axieinfinity.io',
			image: 'https://gateway.pinata.cloud/ipfs/QmTsRJX7r5gyubjkdmzFrKQhHv74p5wT9LdeF1m3RTqrE5',
			price: '0.03ETH',
			currentlySelling: 'True',
			address: '0xe81Bf5A757C4f7F82a2F23b1e59bE45c33c5b13'
		}
	];

	let data: any = sampleData;
</script>

<div>
	<Navbar />
	<div class="flex flex-col place-items-center mt-20">
		<div class="md:text-xl font-bold">Top NFTs</div>
		<div class="flex mt-5 justify-between flex-wrap max-w-screen-xl text-center">
			{#each data as item}
				<NFTTile data={item} />
			{/each}
		</div>
	</div>
</div>
