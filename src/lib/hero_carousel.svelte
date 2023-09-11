<script>
  /** @type {import('./$types').PageData} */

  import { onMount, onDestroy } from 'svelte';
  import Mediaicons from './mediaicons.svelte';
  import { fly } from 'svelte/transition';

  let timer;

  export let images;

  let i = 0;

  function nextImage() {
    i = ( i + 1 ) % images.length;
  }

  onMount(() => {
    timer = setInterval(nextImage, 10 * 1000);
  });

  onDestroy(() => {
    clearInterval(timer);
  });

  $: imgStyle = `background-image: url(${new URL(images[i].path, import.meta.url).href}); background-position: ${images[i].position};`;

</script>

<div class="relative overflow-hidden bg-hero bg-cover bg-no-repeat h-[500px]" style={imgStyle}>
  <div class="absolute top-0 right-0 bottom-0 left-0 h-full w-full overflow-hidden bg-[hsla(0,0%,0%,0.25)] bg-fixed">
    <div class="grid h-full grid-rows-3 md:grid-cols-2 grid-flow-col py-4 px-2">
      <div class="md:col-start-2">
        <slot name="header" />
      </div>
      <div class="col-start-1 row-start-2 md:mx-10 lg:mx-20 self-center grow">
        <slot name="title" />
      </div>
      <footer class="md:col-start-2 row-start-3 bottom-0">
        <slot name="footer" />
      </footer>
    </div>
  </div>
</div>
<hr class="py-5" />
<div class="relative overflow-hidden bg-hero bg-cover bg-no-repeat h-[500px]" style={imgStyle}>
  <div class="absolute top-0 right-0 bottom-0 left-0 h-full w-full overflow-hidden bg-[hsla(0,0%,0%,0.25)] bg-fixed">
    <div class="flex flex-col h-full w-full py-4">
      <div class="basis-1/4 shrink">
        <slot name="header" />
      </div>
      <div class="basis-2/4 md:mx-10 lg:mx-20 grow">
        <slot name="title" />
      </div>
      <div class="basis-1/4 shrink">
        <slot name="footer" />
      </div>
    </div>
  </div>
</div>