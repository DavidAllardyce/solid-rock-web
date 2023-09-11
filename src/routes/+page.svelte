<script>
  import hero_carousel from '../lib/hero_carousel.svelte';

  /** @type {import('./$types').PageData} */
  /*export let data;*/

  import { onMount, onDestroy } from 'svelte';
  import Mediaicons from '../lib/mediaicons.svelte';
  import { fade, fly } from 'svelte/transition';
  import { quintOut } from 'svelte/easing';
  import HeroCarousel from '../lib/hero_carousel.svelte';

  let ready = false;

  const carouselPhotos = [
    { path: '/../home/church_front_sm.jpg', id: 'church-front', position: 'center' },
    { path: '/../home/pastor_sm.jpg', id: 'pastor', position: 'top' },
    { path: '/../home/cornerstone_sm.jpg', id: 'cornerstone', position: 'center' },
    { path: '/../home/praise_team_sm.jpg', id: 'praise=team', position: 'top' },
    { path: '/../home/leadership_team_sm.jpg', id: 'leadership-team', position: 'top' }
  ];

  onMount(() => {
    ready = true;
  });

</script>

<HeroCarousel images={carouselPhotos}>
  <div slot="header" class="text-white">
    <div class="flex justify-end px-2">
      <Mediaicons iconClass="hover:text-cyan-300" />
  </div>
</div>
  <div slot="title" class="flex justify-start items-center h-full w-full">
  <h1 class="text-white text-5xl md:text-5xl xl:text-7xl uppercase">
    Home
  </h1>
</div>
  <div slot="footer" class="justify-self-center">
    {#if ready}
        <div
          class="flex flex-col bg-[hsla(0,0%,0%,0.5)] text-end p-1 flex-nowrap text-white"
          in:fly={{ y: -200, duration: 2000 }}
        >
          <div>Sabbath School 10:00AM</div>
          <div>Worship Service 11:00AM</div>
        </div>
      {/if}
    </div>
</HeroCarousel>

<button
  type="button"
  class="rounded border-2 border-neutral-50 px-[46px] pt-[14px] pb-[12px] text-sm font-medium uppercase leading-normal text-neutral-50 transition duration-150 ease-in-out hover:border-neutral-100 hover:bg-neutral-100 hover:bg-opacity-10 hover:text-neutral-100 focus:border-neutral-100 focus:text-neutral-100 focus:outline-none focus:ring-0 active:border-neutral-200 active:text-neutral-200"
  data-te-ripple-init
  data-te-ripple-color="light"
>
  Join Us
</button>
