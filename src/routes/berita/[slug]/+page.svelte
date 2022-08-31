<script>
	import Newsheader from '$lib/img/newsheader.jpg';
	import Newsimg from '$lib/img/16_9.png';
    import Sharemodal from '../../../lib/component/Sharemodal.svelte';
    import { page } from '$app/stores';

    let url = $page.url.href;


</script>

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
		Lorem ipsum dolor sit amet consectetur adipisicing elit.
	</div>

    <Sharemodal {url}>
        <div class="float-right mr-4 flex h-12 w-12 -translate-y-16 cursor-pointer items-center justify-center rounded-full bg-white hover:bg-sky-100">
            <span class="material-symbols-rounded text-sky-900"> share </span>
        </div>
    </Sharemodal>
    
</div>
<input
	class="absolute -translate-x-96 opacity-0"
	type="text"
	value=""
	id="link"
/>

<main class="container mx-auto">
	<img class="pt-8" src={Newsimg} alt="" />
	<div class="my-8 flex flex-col gap-2">
		<p>
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Praesentium sed assumenda itaque
			minus inventore libero enim, iste voluptas dignissimos rerum nesciunt, tempora saepe voluptate
			incidunt, impedit distinctio quae et ipsa deserunt? Fuga aspernatur provident sed saepe nobis
			magni, deserunt esse aliquam dicta unde tempore necessitatibus officia minus velit asperiores.
			Blanditiis!
		</p>
		<ol>
			<li>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus, eius.</li>
			<li>
				Lorem ipsum dolor sit amet consectetur adipisicing elit. Error vel similique dolore adipisci
				fuga magni iusto mollitia libero fugiat vitae.
			</li>
		</ol>
		<p>
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Ducimus, perferendis esse. Ipsa
			beatae doloremque eligendi veniam, inventore pariatur rem quae delectus, consequatur quos,
			nobis voluptates exercitationem. Tempora, quidem. Id iure odio praesentium exercitationem
			porro modi maxime esse quaerat laborum libero! Ea eaque ratione libero corporis alias!
			Reprehenderit facilis blanditiis impedit?
		</p>
	</div>
</main>

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
