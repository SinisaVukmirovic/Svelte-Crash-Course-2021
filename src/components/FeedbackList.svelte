<script>
    import FeedbackItem from './FeedbackItem.svelte';
    export let feedback = [];
</script>

{#each feedback as fb (fb.id)}
                    <!-- forwarding dispatch event to the above compoents -->
    <FeedbackItem item={fb} on:delete-feedback />
{/each}