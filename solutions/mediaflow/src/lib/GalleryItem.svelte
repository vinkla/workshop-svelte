<script>
  export let name;
  export let image;
  export let size;
</script>

<li class="relative">
  <div
    class="aspect-h-7 aspect-w-10 group block w-full overflow-hidden rounded-lg bg-gray-100 focus-within:ring-2 focus-within:ring-blue-500 focus-within:ring-offset-2 focus-within:ring-offset-gray-100"
  >
    <img
      src={image.src}
      alt={image.alt}
      class="pointer-events-none h-48 w-full object-cover object-center group-hover:opacity-75"
    />
    <button type="button" class="absolute inset-0 focus:outline-none" on:click>
      <span class="sr-only">View details for {name}</span>
    </button>
  </div>
  <p
    class="pointer-events-none mt-2 block truncate text-sm font-medium text-gray-900"
  >
    {name}
  </p>
  <p class="pointer-events-none block text-sm font-medium text-gray-500">
    {(size / Math.pow(1024, 2)).toFixed(1)} MB
  </p>
</li>
