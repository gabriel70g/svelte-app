<script>
import { onMount } from 'svelte';
import { each } from 'svelte/internal';

    let photos = [];
    //console.log('onMount');
    onMount(async () => {
        const response = await fetch('https://rickandmortyapi.com/api/character');
        const  resp = await response.json();
        photos = resp.results;
    });
</script>
<style>
    .Photos{
        width: 100%;
        display: grid;
        grid-template-columns: repeat(5,1fr);
        grid-gap:8px; 
    }
</style>

<div class="Photos">
    {#each photos as photo}
    <figure>
        <img src={photo.image} alt={photo.name}>
        <figcaption>{photo.name}</figcaption>
    </figure>
    {:else}
        <p>Loadding</p>
    {/each}

</div>