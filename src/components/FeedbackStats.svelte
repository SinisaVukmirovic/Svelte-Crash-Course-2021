<script>
    export let count;
    export let average;
</script>

<div class="feedback-ratings">
    <h4>{count} {count === 1 ? 'rating!' : 'ratings!'}</h4>
    <h4>Average ratings: {average}</h4>
</div>

<style>
    .feedback-ratings {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 1rem 5rem;
    }
</style>