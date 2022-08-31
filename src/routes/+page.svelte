<script>
	import img16_9 from '$lib/img/16_9.png';
	import Container from '../lib/component/Container.svelte';
	import { page } from '$app/stores';
	import { each } from 'svelte/internal';

	let array = [0, 1, 2];

	let origin = $page.url.origin;
	async function getBerita() {
		let res = await fetch(
			'https://630f36a2498924524a884049.mockapi.io/api/berita?p=1&l=4&sortBy=createdAt&order=desc'
		);
		let data = await res.json();

		if (res.ok) {
			return data;
		} else {
			throw new Error(data);
		}
	}

	let promiseNews = getBerita();
</script>

<section id="hero">
	<div class="absolute aspect-video w-full bg-black opacity-20" />
	<img src="hero.jpg" alt="" />
</section>
<Container>
	<div class=" grid grid-cols-4 pb-8">
		<section class="col-span-4">
			<div class="section_title my-8">
				<h1 class="text-center text-2xl font-bold text-sky-900">BERITA TERBARU</h1>

				<div class="font-semibold text-sky-700">
					<a class="mx-auto flex w-max" href="{origin}/berita">
						<div>Lihat Semua Berita</div>
						<span class="material-icons"> arrow_right_alt </span>
					</a>
				</div>
			</div>
			{#await promiseNews}
				<div class="lg:flex">
					<div class="p-4 w-full">
						<div class="aspect-video w-full bg-slate-300 animate-pulse" />
						<div class="mt-2 rounded w-40 h-3 bg-slate-200 animate-pulse" />
						<div class="h-4 w-full mt-2 bg-slate-300 rounded" />
						<div class="h-4 w-52 mt-2 bg-slate-300 rounded" />
					</div>
					<div class="w-full">
						{#each array as a}
							<div class="p-4 flex gap-2">
								<div class="aspect-square w-28  bg-slate-300 animate-pulse" />
								<div class="w-3/4">
									<div class="mt-2 rounded w-40 h-3 bg-slate-200 animate-pulse" />
									<div class="h-4 w-full mt-2 bg-slate-300 rounded" />
									<div class="h-4 w-52 mt-2 bg-slate-300 rounded" />
								</div>
							</div>
						{/each}
					</div>
				</div>
			{:then news}
				<div class="lg:flex">
					<div class="m-4">
						<figure class="overflow-hidden aspect-video w-full">
							<a href="{origin}/berita/{news[0].slug}">
								<img class="transition-transform object-cover hover:scale-150" src={news[0].image} alt="" />
							</a>
						</figure>
						<div class="font-semibold uppercase text-slate-400">17 agustus 2022</div>
						<a href="{origin}/berita/{news[0].slug}">
							<h2 class="text-xl font-semibold uppercase hover:text-sky-900">
								{news[0].title}
							</h2>
						</a>
					</div>
					<div>
						{#each news as n, i}
							{#if i != 0}
								<div class="m-4 flex gap-2">
									<div class="overflow-hidden">
										<a href="{origin}/berita/{n.slug}">
											<img
												class="h-28 w-28 object-cover object-center transition-transform hover:scale-150"
												src={n.image}
												alt=""
											/>
										</a>
									</div>
									<div class="w-3/4">
										<div class="text-sm font-semibold uppercase text-slate-400">
											17 agustus 2022
										</div>
										<a href="{origin}/berita/{n.slug}">
											<h2 class="text-lg font-semibold uppercase hover:text-sky-900">
												{n.title}
											</h2>
										</a>
									</div>
								</div>
							{/if}
						{/each}
					</div>
				</div>
				{:catch error}
				<p style="color: red">{error.message}</p>
			{/await}
		</section>
		<section class="col-span-4 lg:col-span-2">
			<div class="section_title my-8 mx-2 ">
				<h1 class="text-center text-2xl font-bold text-sky-900">AGENDA</h1>
			</div>
			<div>
				<div class="m-4 flex gap-4">
					<div class="w-16 rounded border border-sky-900 text-center font-semibold">
						<div class="center_all h-2/3 rounded-t bg-sky-900 text-4xl text-white">17</div>
						<div class="rounded-b bg-white uppercase text-sky-900">agu</div>
					</div>
					<div class="agenda w-3/4">
						<h2 class="agenda_title  text-lg font-semibold">
							Lorem ipsum dolor sit amet consectetur adipisicing elit. Labore, dolores.
						</h2>
						<div class="agenda_ket flex flex-col text-base text-slate-500 md:flex-row md:gap-4">
							<div class="flex ">
								<span class="material-icons mr-2"> schedule </span>
								07:30 - 09-11
							</div>
							<div class="flex">
								<span class="material-icons mr-2"> pin_drop </span>
								UIN Mendalo
							</div>
						</div>
					</div>
				</div>
				<div class="m-4 flex gap-4">
					<div class="w-16 rounded border border-sky-900 text-center font-semibold">
						<div class="center_all h-2/3 rounded-t bg-sky-900 text-4xl text-white">21</div>
						<div class="rounded-b bg-white uppercase text-sky-900">apr</div>
					</div>
					<div class="agenda w-3/4">
						<h2 class="agenda_title  text-lg font-semibold">
							Lorem ipsum dolor sit amet consectetur adipisicing elit. Labore, dolores.
						</h2>
						<div class="agenda_ket flex flex-col text-base text-slate-500 md:flex-row md:gap-4">
							<div class="flex ">
								<span class="material-icons mr-2"> schedule </span>
								07:30 - 09-11
							</div>
							<div class="flex">
								<span class="material-icons mr-2"> pin_drop </span>
								UIN Mendalo
							</div>
						</div>
					</div>
				</div>
			</div>
		</section>
		<section class="col-span-4 lg:col-span-2">
			<div class="section_title my-8 mx-2 ">
				<h1 class="text-center text-2xl font-bold text-sky-900">PENGUMUMAN</h1>
			</div>
			<div class="m-4">
				<div class="flex text-base text-slate-500">
					<div class="flex capitalize">
						<span class="material-icons mr-2"> calendar_month </span>
						kamis, 21 april 2020
					</div>
				</div>
				<h2 class="text-lg font-semibold capitalize">
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla, sed.
				</h2>
			</div>
			<div class="m-4">
				<div class="flex text-base text-slate-500">
					<div class="flex capitalize">
						<span class="material-icons mr-2"> calendar_month </span>
						kamis, 21 april 2020
					</div>
				</div>
				<h2 class="text-lg font-semibold capitalize">
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla, sed.
				</h2>
			</div>
		</section>
	</div>
</Container>

<style>
	.center_all {
		display: flex;
		justify-content: center;
		align-items: center;
	}
</style>
