<script lang="ts">
	import '98.css';

	const f10Handler = (event: KeyboardEvent) => {
		if (event.key === 'F1') {
			window.open('https://github.com/MikeBurton89');
		}
	};
</script>

<div class="parent">
	<div class='list-menu'>
		<ul class="tree-view">
			<li>Who Am I?</li>
			<li>What is web development?</li>
			<li>
                <details>
                   <summary>Front End</summary> 
				<ul>
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
			<li>Special Thanks</li>
		</ul>
	</div>
    <div class='main-title'>
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
    <div class='footer-area'>
        <fieldset ></fieldset>
    </div>
	
    
</div>
<div class="page-container">
	<slot />
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
		grid-column-gap: 0px;
		grid-row-gap: 0px;
	}

	.main-title {
		grid-area: 1 / 4 / 3 / 13;
	}
	.list-menu {
		grid-area: 1 / 1 / 5 / 3;
	}
	.page-container {
		grid-area: 3 / 4 / 7 / 13;
	}
	.footer-area {
		grid-area: 5 / 1 / 7 / 3;
        background-color: #dfdfdf;
	}

    .container {
		display: flex;
		justify-content: space-between;
	}
	.window {
		place-items: center;
		height: 21vh;
	}

	.title-bar-text {
		font-size: 1rem;
	}
	.tree-view {
		width: 100%;
		height: 50%;
	}
</style>
