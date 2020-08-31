<script>
/*Importacion de componentes*/
import Button from './Button.svelte';

/*declareciones*/
let someText = `Frontend Developer free`;
let count = 0;
let styles = {darkmode: false}

function handleClick(){
    count++;
}

function toggle(){
    styles.darkmode = !styles.darkmode
    
    /*trabajando directamente con el DOM*/
    window.document.body.classList.toggle('dark-mode');
}

</script>

<style>
p {
    color: var(--theme-color);

}
</style>

<div class="About">

    {#if !styles.darkmode}
    <p>{someText}</p>
    {:else}
    <p>
        <span>Hello DarMode</span>
    </p>
    {/if}

    <Button text='click' count={count} on:click={handleClick} />
    <Button text='DarkMode' on:click={toggle} />

    <button on:click={handleClick}> click{count===0? '': count}</button>
    <button on:click={toggle}>DarkMode</button>
</div>