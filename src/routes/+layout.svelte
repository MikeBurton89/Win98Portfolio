<script lang="ts">
	import '98.css';
	import ListMenu from '../UI/ListMenu.svelte';
	import MainTitle from '../UI/MainTitle.svelte';
	import MainWindow from '../UI/MainWindow.svelte';
    import Joke from '../UI/Joke.svelte'

	const f10Handler = (event: KeyboardEvent) => {
		if (event.key === 'F1') {
			window.open('https://github.com/MikeBurton89');
		}
	};

	
</script>

<div class="parent">
	<div class="list-menu">
		<ListMenu />
	</div>
	<div class="main-title">
		<MainTitle />
	</div>
	<div class="joke-container">
        <Joke/>
	</div>
	<div class="page-container">
		<MainWindow>
			<slot />
		</MainWindow>
	</div>
</div>

<svelte:window on:keydown|preventDefault={f10Handler} />

<style>
	
	:global(html, body) {
		background-size: cover;
		background-color: #008080;
		font-size: 10px;
        padding: 0.5em;
	}

    :global(p) {
		font-size: 2rem;
	}

	.parent {
		display: grid;
		grid-template-columns: repeat(12, 1fr);
		grid-template-rows: repeat(6, 1fr);
		grid-column-gap: 2rem;
		grid-row-gap: 2rem;
	}

	.main-title {
		grid-area: 1 / 4 / 3 / 13;
	}
	.list-menu {
		grid-area: 1 / 1 / 3 / 4;
        height:100%;
	}
	.joke-container {
		grid-area: 3/1/5/4;
		background-color: #dfdfdf;
		width: 100%;
		height: 100%;
	}
	.page-container {
		grid-area: 3 / 4 / 7 / 13;
	}
	.footer-area {
		grid-area: 5 / 1 / 7 / 4;
	}
</style>
