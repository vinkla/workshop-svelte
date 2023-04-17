<script>
  import { onMount } from 'svelte';
  import { get } from './lib/api';
  import Gallery from './lib/Gallery.svelte';
  import GalleryItem from './lib/GalleryItem.svelte';
  import Panel from './lib/Panel.svelte';

  let files = [];
  let image;

  onMount(async () => {
    files = await get('/1/file/latest?type=image&fields=all');
    files = files.filter((file) => file.gdprStatus === 'OK');
  });

  async function handleOpen(id) {
    const repsonse = await get(`/1/file/${id}?fields=all&jsondata=object`);
    image = repsonse[0];
  }

  function handleClose() {
    image = null;
  }
</script>

<svelte:window
  on:keydown={(event) => event.code === 'Escape' && handleClose()}
/>

<Gallery>
  {#each files as file}
    <GalleryItem
      on:click={() => handleOpen(file.id)}
      image={{
        src: file.mediumPreview,
        alt: file.altText,
      }}
      name={file.filename}
      size={file.filesize}
    />
  {/each}
</Gallery>

{#if image}
  <Panel
    image={{
      src: image.mediumPreview,
      alt: image.altText,
    }}
    name={image.name}
    fileName={image.filename}
    size={image.filesize}
    type={image.type.extension}
    on:click={handleClose}
  />
{/if}
