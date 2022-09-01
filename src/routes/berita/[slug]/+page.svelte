<script>
	import Newsheader from '$lib/img/newsheader.jpg';
	import Newsimg from '$lib/img/16_9.png';
	import Sharemodal from '../../../lib/component/Sharemodal.svelte';
	import { page } from '$app/stores';

	async function getBeritaBySlug(slug) {
		let res = await fetch(`https://630f36a2498924524a884049.mockapi.io/api/berita?slug=${slug}`)
		let data = await res.json();

		// console.log(data);

		if (res.ok) {
			return data;
		} else {
			throw new Error(data);
		}
	}

	const url = $page.url.href;
	const slug = $page.params.slug

	let promiseBerita = getBeritaBySlug(slug)
</script>
{#await promiseBerita}
	<h2 class="h-[800px] font-semibold text-center md:mt-16">
		Loading
	</h2>
{:then berita} 
	{#if berita[0] != undefined}
		<div class="text-2xl">
			<img
				class="absolute -z-10 h-52  object-cover object-center sm:h-auto"
				src={Newsheader}
				alt="news header"
			/>
			<div
				id="header"
				class="flex h-52 w-full  items-end p-10  font-bold uppercase text-white sm:h-auto md:text-4xl"
			>
			{berita[0].title}
			</div>

			<Sharemodal {url}>
				<div
					class="float-right mr-4 flex h-12 w-12 -translate-y-16 cursor-pointer items-center justify-center rounded-full bg-white hover:bg-sky-100"
				>
					<span class="material-icons text-sky-900"> share </span>
				</div>
			</Sharemodal>
		</div>

		<main class="container mx-auto">
			
			<img class="pt-8" src={berita[0].image} alt="" />
			<div class="my-8 flex flex-col gap-2">
				{@html berita[0].body}
			</div>		
			

		</main>
		{:else}
		<h2 class="h-[800px] font-semibold text-center md:mt-16">
			tidak ada berita
		</h2>
	{/if}
{:catch}
<h1>tidak ada berita</h1>
{/await}

<style>
	#header {
		aspect-ratio: 3/1;
		background-color: rgba(0, 0, 0, 0.3);
	}
	p {
		text-indent: 1rem;
	}
	ol {
		margin-left: 2rem;
		list-style-type: decimal;
	}
</style>
