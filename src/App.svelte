<script>
	import FeedbackForm from './components/FeedbackForm.svelte';
	import FeedbackList from './components/FeedbackList.svelte';
	import FeedbackStats from './components/FeedbackStats.svelte';

  // if we are not using stores, our data should be stored in a top level component
  // which is app.svelte
// 	let feedback = [
//   {
//     id: 1,
//     rating: 10,
//     text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.',
//   },
//   {
//     id: 2,
//     rating: 9,
//     text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.',
//   },
//   {
//     id: 3,
//     rating: 8,
//     text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.',
//   },
// ];
// commented out because of solution with using Store

// const addFeedback = (e) => {
//   const newFeedback = e.detail;

//   feedback = [newFeedback, ...feedback];
// }

// const deleteFeedback = (e) => {
//   const itemId = e.detail;
  // The filter() method creates a new array with all elements 
  // that pass the test implemented by the provided function.
//   feedback = feedback.filter(item => item.id != itemId);
// }

// $: count = feedback.length;
// $: average = feedback.reduce((a, {rating}) => a + rating, 0) / count;
// commenting out for solution with Store

</script>
	
<!-- <main class="container">
  <FeedbackForm on:add-feedback={addFeedback} />
  <FeedbackStats {count} {average} /> -->
                  <!-- catching the dispatched event with equal function -->
	<!-- <FeedbackList {feedback} on:delete-feedback={deleteFeedback} />
</main> -->

<!-- STORE SOLUTION -->
<main class="container">
  <FeedbackForm />
  <FeedbackStats />
	<FeedbackList />
</main>

<style>

</style>