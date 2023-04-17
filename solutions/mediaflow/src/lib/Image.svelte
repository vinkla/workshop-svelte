<script>
  export let src;
  export let alt;
</script>

<button on:click class="transition-transform hover:scale-105">
  <img {src} {alt} class="w-52 h-52 object-center object-cover" />
</button>
