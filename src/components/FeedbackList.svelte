<script>
    import { FeedbackStore } from '../stores';

    import { fade, scale } from 'svelte/transition';
    import FeedbackItem from './FeedbackItem.svelte';
    // export let feedback = [];
    // let feedback = [];
    // commented ut because using solution with Stores
</script>

<!-- {#each feedback as fb (fb.id)} -->
                    <!-- forwarding dispatch event to the above compoents -->
    <!-- transitions can't be added on a custom component, -->
    <!-- so, we wrap it in a div  -->
    <!-- <div in:scale out:fade={{ duration: 500 }}>
        <FeedbackItem item={fb} on:delete-feedback />
    </div>
{/each} -->
<!-- commenting out for solution using Store -->

{#each $FeedbackStore as fb (fb.id)}
    <div in:scale out:fade={{ duration: 500 }}>
        <FeedbackItem item={fb} />
    </div>
{/each}