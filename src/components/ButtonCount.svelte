<script>
    import { count } from '../store/store.js'

    function handleClick(){
        count.update(n => n + 1);
    }
</script>
<style>
    button{
        background-color: #f76027;
        color: white;
        border:none;
        border-radius: 05rem;
        text-transform: uppercase;
        cursor: pointer;
    }

</style>

<button on:click={handleClick}>
    <!--Manejo reactivo de la variable -->
    Click  {$count ===0? '': $count}
</button>