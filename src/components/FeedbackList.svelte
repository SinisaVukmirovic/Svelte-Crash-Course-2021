<script>
    import { fade, scale } from 'svelte/transition';
    import FeedbackItem from './FeedbackItem.svelte';
    export let feedback = [];
</script>

{#each feedback as fb (fb.id)}
                    <!-- forwarding dispatch event to the above compoents -->
    <!-- transitions can't be added on a custom component, -->
    <!-- so, we wrap it in a div  -->
    <div in:scale out:fade>
        <FeedbackItem item={fb} on:delete-feedback />
    </div>
{/each}