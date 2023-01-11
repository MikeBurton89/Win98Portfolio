<script lang="ts">
	let dateOfBirth: Date = new Date('06/28/1989');
	let ageDiff: Date = new Date(Date.now() - dateOfBirth.getTime());
	let year: number = ageDiff.getFullYear();
	let age: number = year - 1970;
</script>

<div class="window">
	<div class="title-bar">
		<div class="title-bar-text">Who am I?</div>
		<div class="title-bar-controls">
			<button aria-label="Minimize" />
			<button aria-label="Maximize" />
			<button aria-label="Close" />
		</div>
	</div>
	<div class="window-body">
		<p>I'm a {age} years old web developer from Italy.</p>
	</div>
</div>

<style>
</style>
