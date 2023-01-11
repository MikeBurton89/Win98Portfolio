<script lang="ts">
	import { onMount } from 'svelte';

	type JokeResponse = {
		error: boolean;
		category: string;
		type: string;
		joke: string;
		flags: {};
		id: number;
		safe: boolean;
		lang: string;
		message?: string;
	};

	let joke: string;

	onMount(() => {
		try {
			fetch('https://v2.jokeapi.dev/joke/Programming?type=single')
				.then((res) => res.json())
				.then((body: JokeResponse) => {
					if (body.error === false) {
						joke = body.joke;
					} else {
						throw new Error(body.message);
					}
				});
		} catch (error) {
			console.log(error);
		}
	});
</script>

<div class="window">
	<div class="title-bar inactive">
		<div class="title-bar-text">A little random programming joke...</div>
	</div>
	<div class="window-body">
		<fieldset>
			<h3>
				{joke !== undefined ? joke : ''}
			</h3>
		</fieldset>
	</div>
</div>

<style>
	.window {
		height: 100%;
		width: 100%;
	}

	.window-body {
		display: flex;
		max-width: 100%;
	}
	fieldset {
		width: 100%;
		height: 100%;
		overflow: auto;
	}
</style>
