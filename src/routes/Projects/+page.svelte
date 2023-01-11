<script>
	import { title } from '../../stores';
	import { onMount } from 'svelte';
	onMount(() => ($title = 'Projects'));
</script>

<p>{`Here's a list of projects`}</p>
<select>
	<option>5 - Incredible!</option>
	<option>4 - Great!</option>
	<option>3 - Pretty good</option>
	<option>2 - Not so great</option>
	<option>1 - Unfortunate</option>
</select>
