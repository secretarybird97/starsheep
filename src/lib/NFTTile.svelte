<script lang="ts">
	import { GetIpfsUrlFromPinata } from '$lib/utils';
	export let data: any;

	const newTo = { pathname: '/nftPage' + data.data.tokenId };

	const IPFSUrl = GetIpfsUrlFromPinata(data.data.image);
</script>

<a href={newTo.pathname}>
	<div
		class="border-2 ml-12 mt-5 mb-12 flex flex-col items-center rounded-lg w-48 md:w-72 shadow-2xl"
	>
		<img src={IPFSUrl} alt="" class="w-72 h-48 rounded-lg object-cover" />
		<div class="w-full p-2 bg-gradient-to-t from-[#454545] to-transparent rounded-lg pt-5 -mt-20">
			<strong class="text-xl">{data.data.name}</strong>
			<p>{data.data.description}</p>
		</div>
	</div></a
>
