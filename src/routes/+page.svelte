<script lang="ts">
    import { title } from "../stores";
	import { onMount } from "svelte"
    onMount(()=> $title = 'Who am I?')
	let dateOfBirth: Date = new Date('06/28/1989');
	let ageDiff: Date = new Date(Date.now() - dateOfBirth.getTime());
	let year: number = ageDiff.getFullYear();
	let age: number = year - 1970;
</script>

<p>{`I'm a ${age} years old web developer from Italy.`}</p>

<style>
</style>
