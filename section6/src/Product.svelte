<script>
    import { createEventDispatcher } from 'svelte';

    export let title;
    export let price;
    export let bestseller = true;

    const dispatch = createEventDispatcher();

    function addToCart() {
        dispatch('add-to-cart', {id: 'p1'});
    }

</script>

<!-- <article on:click="{() => console.log("Jo")}"> -->
<article>
    <h1>{title}</h1>
    <h2>${price}</h2>

    {#if bestseller}
        <h3>BEST SELLER</h3> 
    {/if}

    <button on:click="{addToCart}">Add to Cart</button>
    <button on:click="{() =>{dispatch('delete', 'p1')}}">Delete</button>
</article>