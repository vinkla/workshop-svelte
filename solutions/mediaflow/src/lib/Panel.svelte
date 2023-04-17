<script>
  import { fly } from 'svelte/transition';
  import X from './X.svelte';
  import Overlay from './Overlay.svelte';

  export let name;
  export let fileName;
  export let image;
  export let size;
  export let type;

  let details = [
    { label: 'Name', value: fileName },
    { label: 'Size', value: (size / Math.pow(1024, 2)).toFixed(1) + ' MB' },
    { label: 'Type', value: type.toUpperCase() },
  ];
</script>

<div
  class="relative z-10"
  aria-labelledby="slide-over-title"
  role="dialog"
  aria-modal="true"
>
  <Overlay />

  <div class="fixed inset-0 overflow-hidden">
    <div class="absolute inset-0 overflow-hidden">
      <div
        class="pointer-events-none fixed inset-y-0 right-0 flex max-w-full pl-10"
        transition:fly={{ duration: 200, x: 200 }}
      >
        <div class="pointer-events-auto w-screen max-w-md">
          <div
            class="flex h-full flex-col overflow-y-scroll bg-white pb-6 shadow-xl"
          >
            <img
              src={image.src}
              alt={image.alt}
              class="pointer-events-none w-full object-cover object-center group-hover:opacity-75"
            />
            <div class="mt-6 px-4 sm:px-6">
              <div class="flex items-start justify-between">
                <h2
                  class="text-base font-semibold leading-6 text-gray-900"
                  id="slide-over-title"
                >
                  {name}
                </h2>
                <div class="ml-3 flex h-7 items-center">
                  <X on:click />
                </div>
              </div>
            </div>
            <div class="relative mt-6 flex-1 px-4 sm:px-6">
              <dl class="divide-y divide-gray-100">
                {#each details as { label, value }}
                  <div
                    class="px-4 py-6 sm:grid sm:grid-cols-3 sm:gap-4 sm:px-0"
                  >
                    <dt class="text-sm font-medium leading-6 text-gray-900">
                      {label}
                    </dt>
                    <dd
                      class="mt-1 text-sm leading-6 text-gray-700 sm:col-span-2 sm:mt-0"
                    >
                      {value}
                    </dd>
                  </div>
                {/each}
              </dl>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
