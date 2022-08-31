<script>
	import { page } from '$app/stores';

	console.log($page.error);
</script>

<h1 class="mt-8 text-center text-5xl uppercase">{$page.error.name}</h1>
<h2>{$page.error.message}</h2>
