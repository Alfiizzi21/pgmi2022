<script>
	import logo from './pgmi.png';

	let y;
	let headerclass;
	let nav_toggle = true;
	let navclass;

	$: if (nav_toggle) {
		navclass = '-translate-y-[1000px]';
	} else {
		navclass = '-translate-y-0';
	}

	$: if (y > 10) {
		headerclass = 'md:bg-sky-900';
	} else {
		headerclass = 'md:bg-transparent';
	}
</script>

<header
	class="relative z-50 flex h-16 w-full items-center justify-between bg-sky-900 transition-colors duration-300 md:fixed {headerclass}"
>
	<img class="mx-4 h-14" src={logo} alt="pgmi log" />
	<div class="h-10 w-10 md:hidden">
		<label class="cursor-pointer" for="nav-toggle">
			{#if nav_toggle}
				<span class="material-symbols-rounded text-white pt-2">menu</span>
			{:else}
				<span class="material-symbols-rounded text-white pt-2">close</span>
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

	<nav class="absolute top-16 left-0 right-0 md:relative md:top-0 md:mx-4 md:-translate-y-0 transition-transform {navclass}">
		<ul class="flex h-full flex-col gap-1 bg-sky-900 pb-4 md:flex-row md:bg-transparent md:pb-0">
			<li
				class="flex h-11 w-full items-center px-4 hover:text-sky-300 md:h-16 "
			>
				Beranda
			</li>
            <li
				class="group flex w-full flex-col gap-1 px-4 hover:text-sky-300 md:h-16 md:flex-row md:items-center "
			>
				<div class="flex h-11 items-center">
					Informasi <span class="material-symbols-rounded">expand_more</span>
				</div>
				<ul class="md:absolute md:top-12 md:hidden md:bg-sky-700 md:group-hover:block">
					<a href="alfi">
						<li class="py-2 px-6 hover:text-sky-300 md:p-4 md:hover:bg-sky-900 md:hover:text-white">
							Berita
						</li></a
					>
					<li class=" py-2 px-6 hover:text-sky-300 md:p-4 md:hover:bg-sky-900 md:hover:text-white">
						Pengumuman
					</li>
				</ul>
			</li>
            
			<li
				class="group flex w-full flex-col gap-1 px-4 hover:text-sky-300 md:h-16 md:flex-row md:items-center "
			>
				<div class="flex h-11 items-center">
					Profil <span class="material-symbols-rounded">expand_more</span>
				</div>
				<ul class="md:absolute md:top-12 md:hidden md:bg-sky-700 md:group-hover:block">
					<a href="alfi">
						<li class="py-2 px-6 hover:text-sky-300 md:p-4 md:hover:bg-sky-900 md:hover:text-white">
							Visi Dan Misi
						</li></a
					>
					<li class=" py-2 px-6 hover:text-sky-300 md:p-4 md:hover:bg-sky-900 md:hover:text-white">
						Struktur Organisasi
					</li>
				</ul>
			</li>
			<li
				class="group flex w-full flex-col gap-1 px-4 hover:text-sky-300 md:h-16 md:flex-row md:items-center "
			>
				<div class="flex h-11 items-center">
					Akademik<span class="material-symbols-rounded">expand_more</span>
				</div>
				<ul class="md:absolute md:top-12 md:hidden md:bg-sky-700 md:group-hover:block">
					<li class="py-2 px-6 hover:text-sky-300 md:p-4 md:hover:bg-sky-900 md:hover:text-white">Kurikulum</li>
					<li class="py-2 px-6 hover:text-sky-300 md:p-4 md:hover:bg-sky-900 md:hover:text-white">
						Jadwal Perkuliahan
					</li>
				</ul>
			</li>
            <li
				class="flex h-11 w-full items-center px-4 hover:text-sky-300 md:h-16 "
			>
				Kontak
			</li>
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
