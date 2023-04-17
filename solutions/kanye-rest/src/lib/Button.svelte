<script>
  export let role = 'button';
</script>

<button {role} on:click>
  <slot />
</button>

<style>
  button {
    background-color: white;
    border-radius: 1rem;
    border: none;
    cursor: pointer;
    font-size: 1.5rem;
    padding: 1rem;
  }
</style>
