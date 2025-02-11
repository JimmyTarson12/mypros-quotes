<script lang="ts">
  let error: any
  let randromlyGeneratedQuote: string
  let randromlyGeneratedQuoteAuthor: string

  let firsttime = true

  const quotes = [
    {
        text: "Life is what happens when you're busy making other plans.",
        author: "John Lennon",
    },
    {
        text: "The future belongs to those who believe in the beauty of their dreams.",
        author: "Eleanor Roosevelt",
    },
    {
        text: "Success is not final, failure is not fatal: it is the courage to continue that counts.",
        author: "Winston Churchill",
    },
    {
        text: "The only way to do great work is to love what you do.",
        author: "Steve Jobs",
    },
    {
        text: "Be the change you wish to see in the world.",
        author: "Mahatma Gandhi",
    },
    {
        text: "Everything you've ever wanted is on the other side of fear.",
        author: "George Addair",
    },
    {
        text: "The best time to plant a tree was 20 years ago. The second best time is now.",
        author: "Chinese Proverb",
    },
    {
        text: "It does not matter how slowly you go as long as you do not stop.",
        author: "Confucius",
    },
    {
        text: "Whether you think you can or you think you can't, you're right.",
        author: "Henry Ford",
    },
    {
        text: "The only limit to our realization of tomorrow will be our doubts of today.",
        author: "Franklin D. Roosevelt",
    }
  ];
  function generateQuote() {
    try {
      randromlyGeneratedQuote = quotes[Math.floor(Math.random() * quotes.length)].text
      randromlyGeneratedQuoteAuthor = quotes[Math.floor(Math.random() * quotes.length)].author

      firsttime = false
    } catch (err) {
      error = err
    }
  }
</script>

<main>
  <h1>Mypros Quotes</h1>
{#if error}
  <p class="error">Error finding quote</p>
{:else if !error && !firsttime}
  <p id="quote">"{randromlyGeneratedQuote}"</p>
  <p id="author">{randromlyGeneratedQuoteAuthor}</p>
{/if}
  <button on:click={generateQuote}>Generate Quote</button>
</main>

<style>
  .error {
    color: #FF0000;
  }
  #quote {
    font-weight: bold;
    color: #646cff;
  }
  #author {
    color: #888;
    font-style: italic;
  }
</style>