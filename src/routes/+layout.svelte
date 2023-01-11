<script lang="ts">
	import '98.css';

	const f10Handler = (event: KeyboardEvent) => {
		if (event.key === 'F1') {
			window.open('https://github.com/MikeBurton89');
		}
	};
</script>

<div class="parent">
	<div class="list-menu">
		<ul class="tree-view">
			<li><a href="/">Who Am I?</a> </li>
			<li>
				<details>
					<summary><a href="/Projects">Projects</a> </summary>
					<ul>
						<li>React</li>
						<li>Svelte</li>
						<li>HTML/CSS/Javascript</li>
						<li>React</li>
						<li>Svelte</li>
						<li>HTML/CSS/Javascript</li>
					</ul>
				</details>
			</li>
			<li>
				<details open>
					<summary>JavaScript</summary>
					<ul>
						<li>Avoid at all costs</li>
						<li>
							<details>
								<summary>Unless</summary>
								<ul>
									<li>Avoid</li>
									<li>
										<details>
											<summary>At</summary>
											<ul>
												<li>Avoid</li>
												<li>At</li>
												<li>All</li>
												<li>Cost</li>
											</ul>
										</details>
									</li>
									<li>All</li>
									<li>Cost</li>
								</ul>
							</details>
						</li>
					</ul>
				</details>
			</li>
			<li><a href="SpecialThanks">Special Thanks</a> </li>
		</ul>
	</div>
	<div class="main-title">
		<div class="window">
			<div class="title-bar">
				<div class="title-bar-text">An old school portfolio for an old school developer</div>
				<div class="title-bar-controls">
					<button aria-label="Minimize" />
					<button aria-label="Maximize" />
					<button aria-label="Close" />
				</div>
			</div>
			<div class="window-body">
				<h1>Welcome to Mike's Portfolio</h1>
				<div class="status-bar">
					<p class="status-bar-field">
						Press F1 or click
						<a target="_blank" href="https://github.com/MikeBurton89">Here</a>
						to see my GitHub
					</p>
				</div>
			</div>
		</div>
	</div>
	<fieldset class="footer-area">
		<div />
	</fieldset>
	<div class="page-container">
		<slot />
	</div>
</div>

<svelte:window on:keydown|preventDefault={f10Handler} />

<style>
	:global(html) {
		background-size: cover;
		background-color: #008080;
		font-size: 10px;
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
		grid-area: 1 / 1 / 5 / 4;
	}
	.page-container {
		grid-area: 3 / 4 / 7 / 13;
	}
	.footer-area {
		grid-area: 5 / 1 / 7 / 4;
		background-color: #dfdfdf;
	}

	.window {
		place-items: center;
	}

	.title-bar-text {
		font-size: 1rem;
	}
</style>
