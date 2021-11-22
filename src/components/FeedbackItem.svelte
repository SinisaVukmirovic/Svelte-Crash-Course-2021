<script>
    import Card from './Card.svelte';
    export let item;
</script>

<Card>
    <h3>{item.rating}</h3>
    <h4>{item.text}</h4>
</Card>