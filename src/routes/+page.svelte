<script lang="ts">
	const f10Handler = (event: KeyboardEvent) => {
		if (event.key === 'F1') {
			window.open('https://github.com/MikeBurton89');
		}
	};
</script>

<div class="container">
	<div>
		<ul class="tree-view">
			<li>Table of Contents</li>
			<li>What is web development?</li>
			<li>
				CSS
				<ul>
					<li>Selectors</li>
					<li>Specificity</li>
					<li>Properties</li>
				</ul>
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
			<li>HTML</li>
			<li>Special Thanks</li>
		</ul>
	</div>
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
					Press F1 or click <a target="_blank" href="https://github.com/MikeBurton89">Here</a>
                    to see my GitHub
				</p>
			</div>
		</div>
	</div>
</div>

<svelte:window on:keydown|preventDefault={f10Handler} />

<div>
	<p>Visit to see my GitHub</p>
	<button>Button</button>
</div>

<style>
	.container {
		display: flex;
		justify-content: space-between;
	}
	.window {
		place-items: center;
		width: 70vw;
		height: 21vh;
	}

	.title-bar-text {
		font-size: 1rem;
	}
	.tree-view {
		width: 100%;
		height: 100%;
	}
</style>
