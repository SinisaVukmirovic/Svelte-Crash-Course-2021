<script>
    import { FeedbackStore } from '../stores';

    // export let count;
    // export let average;
    // commenting out for store solution

    $: count = $FeedbackStore.length;
    $: average = $FeedbackStore.reduce((a, {rating}) => a + rating, 0) / count;
</script>

<div class="feedback-ratings">
    <h4>{count} {count === 1 ? 'rating!' : 'ratings!'}</h4>
    <h4>Average ratings: {average.toFixed(2)}</h4>
</div>

<style>
    .feedback-ratings {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 1rem 5rem;
    }
</style>