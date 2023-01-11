<script lang="ts">
    import { title } from "../stores";
	import ModalWindow from "./ModalWindow.svelte";
    let showModal:boolean = false
</script>
<div class="window">
	<div class="title-bar">
		<div class="title-bar-text">{$title}</div>
		<div class="title-bar-controls">
			<button aria-label="Minimize" />
			<button aria-label="Maximize" />
			<button aria-label="Close" on:click={(e)=> showModal = true} />
		</div>
	</div>
	<div class="window-body">
        <fieldset>
            <slot/>
        </fieldset>
	</div>
</div>
{#if showModal === true}
<ModalWindow on:close={()=> showModal = false}>
    <div class="window">
        <div class="title-bar">
            <div class="title-bar-text">NICE TRY!</div>
        </div>
        <div class="window-body">
            <h2>
                Unfortunately you cannot close any window on this website, but kudos for trying...
            </h2>
        </div>
    </div>
</ModalWindow>
    
{/if}

<style>
    .window{
        max-height: 100%;
    }
    .window-body{
        display:flex;
        max-height: 100%;
    }
    fieldset{
        height: 40rem;
        width: 100%;
        background-color: #FFFFFF;
        overflow: auto;
    }
</style>
