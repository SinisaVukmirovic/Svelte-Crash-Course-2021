<script>
    import { createEventDispatcher } from 'svelte';

    import Card from './Card.svelte';
    export let item;

    // when our data is in top level component
    // we need to dispatch that event up to the component
    // that stores our data, then we can change them
    const dispatch = createEventDispatcher();

    const handleDelete = (itemId) => {
        dispatch('delete-feedback', itemId);
    }
</script>

<Card>
    <div class="num-display">
        {item.rating}
    </div>

    <!-- when calling functions with arguments in it -->
    <!-- we first need to call a function with ()=> that then calls that function -->
    <button on:click={() => handleDelete(item.id)} class="close">&#10060;</button>
    <div class="text-display">
        {item.text}
    </div>
</Card>

<style>
    .num-display {
        position: absolute;
        top: -10px;
        left: -10px;
        width: 50px;
        height: 50px;
        background: #ff6a95;
        color: #fff;
        border: 1px #eee solid;
        border-radius: 50%;
        padding: 10px;
        text-align: center;
        font-size: 19px;
    }
  .close {
    position: absolute;
    top: 10px;
    right: 20px;
    cursor: pointer;
    background: none;
    border: none;
  }
</style>