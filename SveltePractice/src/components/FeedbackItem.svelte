<script>
    import {createEventDispatcher} from 'svelte';
    import Card from './Card.svelte';
    export let item ;

    const dispatch = createEventDispatcher()

    const Handledelete = (itemId) =>{
        dispatch('delete-feedback',itemId);
    }
</script>

<Card>
    <div class="item-rating">
        {item.rating}
    </div>
    <button class="item-close" on:click= {()=> Handledelete(item.id)}>X</button>
    <div class="item-text">
        {item.text}
    </div>
</Card>

<style>
    .item-rating{
        position: absolute;
        top:-10px;
        left:-10px;
        background-color: #FF6A95;
        color: #fff;
        width: 50px;
        height: 50px;
        padding: 10px;
        border-radius: 50%;
        border: 1px #eee solid;
        text-align: center;
        font-size: 19px;
    }

    .item-close{
        position: absolute;
        top: 5px;
        right: 10px;
        cursor: pointer;
        background: none;
        border: none;
    }
</style>