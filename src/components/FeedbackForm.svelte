<script>
    // external module for unique ID creation
    import { v4 as uuidv4 } from 'uuid';
    import { createEventDispatcher } from 'svelte';

    import Card from './Card.svelte';
    import Button from './Button.svelte';
    import RatingSelect from './RatingSelect.svelte';

    const dispatch = createEventDispatcher(); 

    let text = '';
    let rating = 10;
    let btnDisabled = true;
    let minChars = 10;
    let message;

    const handleSelect = e => rating = e.detail;

    const handleInput = () => {
      if (text.trim().length <= minChars) {
        message = `Text must be at least ${minChars} characters!`;
        btnDisabled = true;
      } else {
        message = null;
        btnDisabled = false;
      }
    }

    const handleSubmit = () => {
      if (text.trim().length > minChars) {
        const newFeedback = {
          id: uuidv4(),
          text,
          // adding + before var to turn it into a number instead of a(default) string
          rating: +rating
        }

        dispatch('add-feedback', newFeedback);

        text = '';
        document.querySelector('#text-input').focus();
      }
    }
</script>

<Card>
    <header>
        <h2>How would you rate your service with us?</h2>
    </header>
    <form on:submit|preventDefault={handleSubmit}>
        <RatingSelect on:rating-select={handleSelect} />
        <div class="input-group">
            <input id='text-input' type="text" on:input={handleInput} bind:value={text} placeholder="Tell us something that keeps you coming back">
            <Button disabled={btnDisabled} type="submit">Send</Button>
        </div>
        {#if message}
          <div class="message">
            {message}
          </div>
        {/if}
    </form>
</Card>

<style>
header {
    max-width: 400px;
    margin: auto;
  }
  header h2 {
    font-size: 22px;
    font-weight: 600;
    text-align: center;
  }
  .input-group {
    display: flex;
    flex-direction: row;
    border: 1px solid #ccc;
    padding: 8px 10px;
    border-radius: 8px;
    margin-top: 15px;
  }
  input {
    flex-grow: 2;
    border: none;
    font-size: 16px;
    padding: 0 1rem;
  }
  input:focus {
    outline: none;
  }
  .message{
    padding-top: 10px;
    text-align: center;
    color: rebeccapurple;
  }
</style>