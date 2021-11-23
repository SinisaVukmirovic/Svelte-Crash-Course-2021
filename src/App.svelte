<script>
	import FeedbackList from './components/FeedbackList.svelte';

  // if we are not using stores, our data should be stored in a top level component
  // which is app.svelte
	let feedback = [
  {
    id: 1,
    rating: 10,
    text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.',
  },
  {
    id: 2,
    rating: 9,
    text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.',
  },
  {
    id: 3,
    rating: 8,
    text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.',
  },
];

const deleteFeedback = (e) => {
  const itemId = e.detail;
  // The filter() method creates a new array with all elements 
  // that pass the test implemented by the provided function.
  feedback = feedback.filter(item => item.id != itemId);
}
</script>
	
<main class="container">
	<FeedbackList {feedback} on:delete-feedback={deleteFeedback} />
</main>

<style>
	
</style>