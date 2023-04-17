<script>
  import Button from './lib/Button.svelte';

  let quote = 'Click the button to get a quote';

  async function handleClick() {
    const response = await fetch('https://api.kanye.rest/');
    const data = await response.json();
    quote = data.quote;
  }
</script>

<main>
  <p>{quote}</p>
  <Button on:click={handleClick}>🔄 ye</Button>
</main>

<style>
  main {
    align-items: center;
    display: flex;
    flex-direction: column;
    gap: 1rem;
    height: 100vh;
    justify-content: center;
  }

  p {
    font-size: 2rem;
    margin: 0 auto;
    max-width: 700px;
    text-align: center;
    width: 100%;
  }
</style>
