<script>
	import logo from './pgmi.png';
	import { page } from '$app/stores';

	let y;
	let headerclass;
	let nav_toggle = true;
	let navclass;
	let host = $page.url.origin;

	$: if (nav_toggle) {
		navclass = '-translate-y-[1000px]';
	} else {
		navclass = '-translate-y-0';
	}

	$: if (y > 10 || !($page.url.pathname == '/')) {
		headerclass = 'md:bg-sky-900';
	} else {
		headerclass = 'md:bg-transparent';
	}

	function closeNav() {
		if (!nav_toggle) {
			nav_toggle = true;
		}
	}
</script>

<header
	
	class="relative z-50 flex h-16 w-full items-center justify-between bg-sky-900 transition-colors duration-300 md:fixed md:top-0 {headerclass}"
>
	<a href={host}>
		<img class="mx-4 h-10" src={logo} alt="pgmi logo" />
	</a>
	<div class="h-10 w-10 md:hidden">
		<label class="cursor-pointer" for="nav-toggle">
			{#if nav_toggle}
				<span class="material-symbols-rounded pt-2 text-white">menu</span>
			{:else}
				<span class="material-symbols-rounded pt-2 text-white">close</span>
			{/if}
		</label>
		<input
			class="hidden"
			type="checkbox"
			bind:checked={nav_toggle}
			name="nav-toggle"
			id="nav-toggle"
		/>
	</div>

	<nav
		on:click={closeNav} class="absolute top-16 left-0 right-0 transition-transform md:relative md:top-0 md:mx-4 md:-translate-y-0 {navclass}"
	>
		<ul class="flex h-full flex-col gap-1 bg-sky-900 pb-4 md:flex-row md:bg-transparent md:pb-0">
			<a href={host}>
				<li class="flex h-11 w-full items-center px-4 hover:text-sky-600 md:h-16 ">Beranda</li>
			</a>
			<li
				class="group flex w-full flex-col gap-1 px-4 hover:text-sky-600 md:h-16 md:flex-row md:items-center "
			>
				<div class="flex h-11 items-center">
					Profil <span class="material-symbols-rounded">expand_more</span>
				</div>
				<ul class="md:absolute md:top-12 md:hidden md:bg-sky-700 md:group-hover:block">
					<a href="{host}/profil/#visi-misi">
						<li
							class=" py-2 px-6 hover:text-sky-600 md:p-4 md:hover:bg-sky-900 md:hover:text-white"
						>
							Visi Dan Misi
						</li>
					</a>
					<a href="{host}/profil/#struktur-organisasi">
						<li
							class=" py-2 px-6 hover:text-sky-600 md:p-4 md:hover:bg-sky-900 md:hover:text-white"
						>
							Struktur Organisasi
						</li>
					</a>
				</ul>
			</li>
			<a href="{host}/berita">
				<li class="flex h-11 w-full items-center px-4 hover:text-sky-600 md:h-16 ">Berita</li>
			</a>
			<!-- <li
				class="group flex w-full flex-col gap-1 px-4 hover:text-sky-600 md:h-16 md:flex-row md:items-center "
			>
				<div class="flex h-11 items-center">
					Informasi <span class="material-symbols-rounded">expand_more</span>
				</div>
				<ul class="md:absolute md:top-12 md:hidden md:bg-sky-700 md:group-hover:block">
					<li class="py-2 px-6 hover:text-sky-600 md:p-4 md:hover:bg-sky-900 md:hover:text-white">
						Berita
					</li>
					<li class=" py-2 px-6 hover:text-sky-600 md:p-4 md:hover:bg-sky-900 md:hover:text-white">
						Pengumuman
					</li>
				</ul>
			</li> -->
			<li
				class="group flex w-full flex-col gap-1 px-4 hover:text-sky-600 md:h-16 md:flex-row md:items-center "
			>
				<div class="flex h-11 items-center">
					Akademik<span class="material-symbols-rounded">expand_more</span>
				</div>
				<ul class="md:absolute md:top-12 md:hidden md:bg-sky-700 md:group-hover:block">
					<li class="py-2 px-6 hover:text-sky-600 md:p-4 md:hover:bg-sky-900 md:hover:text-white">
						Kurikulum
					</li>
					<li class="py-2 px-6 hover:text-sky-600 md:p-4 md:hover:bg-sky-900 md:hover:text-white">
						Jadwal Perkuliahan
					</li>
				</ul>
			</li>
			<a href="#kontak">
				<li class="flex h-11 w-full items-center px-4 hover:text-sky-600 md:h-16 ">Kontak</li></a
			>
		</ul>
	</nav>
</header>
<svelte:window bind:scrollY={y} />

<style>
	@import url('https://fonts.googleapis.com/css2?family=Open+Sans&display=swap');
	header {
		font-family: 'Open Sans', sans-serif;
	}
	li {
		color: white;
		cursor: pointer;
	}
</style>
