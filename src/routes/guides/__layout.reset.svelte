<script>
	import Title from '$lib/title.svelte';
	import { fly } from 'svelte/transition';
	import '../../styles/global.css';
</script>

<header>
	<nav transition:fly={{ x: -200, duration: 500, delay: 300 }}>
		<Title title="Ninja Gaming Guides" />
		<div class="links">
			<a href="/">Home</a>
			<a href="/about">About</a>
			<a href="/guides">Guides</a>
		</div>
	</nav>
</header>
<main>
	<slot />
</main>
<footer>
	<p>Copyright 2022 Net Nija</p>
</footer>

<style>
	header {
		text-align: center;
		background-color: rgba(0, 0, 0, 0.1);
	}

	main {
		max-width: 960px;
		margin: 20px auto;
	}

	footer {
		text-align: center;
	}

	.links {
		margin-left: auto;
	}

	a {
		margin-left: 10px;
	}

	nav {
		display: flex;
		align-items: center;
		max-width: 960px;
		margin: 0 auto;
	}
</style>
