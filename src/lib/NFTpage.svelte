<script lang="ts">
	import Navbar from './Navbar.svelte';
	import { GetIpfsUrlFromPinata } from './utils';

	export let props: any;

	let data: any = {};
	let message: string = '';
	let currAddress: string = '0x';
</script>

<div class="min-h-screen">
	<Navbar />
	<div class="flex ml-20 mt-20">
		<img src={data.image} alt="" class="w-2/5" />
		<div class="text-xl ml-20 space-y-8 shadow-2xl rounded-lg border-2 p-5">
			<div>
				Name: {data.name}
			</div>
			<div>
				Description: {data.description}
			</div>
			<div>
				Price: <span class="">{data.price} ETH</span>
			</div>
			<div>
				Owner: <span class="text-sm">{data.owner}</span>
			</div>
			<div>
				Seller: <span class="text-sm">{data.seller}</span>
			</div>
			<div>
				{#if currAddress != data.owner && currAddress != data.seller}
					<button class="btn" />
				{:else}
					<div class="">You are the owner of this NFT</div>
				{/if}
			</div>
			<div class="text-center mt-3">{message}</div>
		</div>
	</div>
</div>
