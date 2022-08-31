<script>
	import img16_9 from '$lib/img/16_9.png';
	import Container from '../lib/component/Container.svelte';
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
	
				<div class="flex justify-center font-semibold text-sky-700">
					<div>Lihat Semua Berita</div>
					<span class="material-symbols-rounded"> arrow_right_alt </span>
				</div>
			</div>
			<div class="lg:flex">
				<div class="group m-4">
					<figure class="overflow-hidden">
						<img class="transition-transform group-hover:scale-150" src={img16_9} alt="" />
					</figure>
					<div class="font-semibold uppercase text-slate-400">17 agustus 2022</div>
					<h2 class="text-xl font-semibold uppercase group-hover:text-sky-900">
						Lorem ipsum dolor sit amet consectetur, adipisicing elit. Qui, impedit.
					</h2>
				</div>
	
				<div>
					<div class="group m-4 flex gap-2">
						<div class="overflow-hidden">
							<img
								class="h-28 w-28 object-cover object-center transition-transform group-hover:scale-150"
								src={img16_9}
								alt=""
							/>
						</div>
						<div class="w-3/4">
							<div class="text-sm font-semibold uppercase text-slate-400">17 agustus 2022</div>
							<h2 class="text-lg font-semibold uppercase hover:text-sky-900">
								Lorem ipsum dolor sit amet consectetur, adipisicing elit. Qui, impedit.
							</h2>
						</div>
					</div>
	
					<div class="group m-4 flex gap-2">
						<div class="overflow-hidden">
							<img
								class="h-28 w-28 object-cover object-center transition-transform group-hover:scale-150"
								src={img16_9}
								alt=""
							/>
						</div>
						<div class="w-3/4">
							<div class="font-semibold uppercase text-slate-400">17 agustus 2022</div>
							<h2 class="text-lg font-semibold uppercase hover:text-sky-900">
								Lorem ipsum dolor sit amet consectetur, adipisicing elit. Qui, impedit.
							</h2>
						</div>
					</div>
	
					<div class="group m-4 flex gap-2">
						<div class="overflow-hidden">
							<img
								class="h-28 w-28 object-cover object-center transition-transform group-hover:scale-150"
								src={img16_9}
								alt=""
							/>
						</div>
						<div class="w-3/4">
							<div class="font-semibold uppercase text-slate-400">17 agustus 2022</div>
							<h2 class="text-lg font-semibold uppercase hover:text-sky-900">
								Lorem ipsum dolor sit amet consectetur, adipisicing elit. Qui, impedit.
							</h2>
						</div>
					</div>
				</div>
			</div>
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
								<span class="material-symbols-rounded mr-2"> schedule </span>
								07:30 - 09-11
							</div>
							<div class="flex">
								<span class="material-symbols-rounded mr-2"> pin_drop </span>
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
								<span class="material-symbols-rounded mr-2"> schedule </span>
								07:30 - 09-11
							</div>
							<div class="flex">
								<span class="material-symbols-rounded mr-2"> pin_drop </span>
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
						<span class="material-symbols-rounded mr-2"> calendar_month </span>
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
						<span class="material-symbols-rounded mr-2"> calendar_month </span>
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
