<svelte:head>
  <title>Gallery</title>
</svelte:head>

<script>
  import { onMount } from "svelte";
  onMount(() => {
    const observer = new IntersectionObserver(f, {
      threshold: [0, 1],
    });

    function f(entries) {
      for (const entry of entries) {
        if (entry.isIntersecting && entry.intersctionRatio >= 1) {
          entry.target.classList.toggle("inbound", true);
        } else {
          entry.target.classList.toggle("inbound", false);
        }
      }
    }
    const itemEls = Array.from(document.querySelectorAll(".item"));
    for (const itemEl of itemEls) observer.observe(itemEl);
  });
  const images = [
    "https://source.unsplash.com/featured?98",
    "https://source.unsplash.com/featured?97",
    "https://source.unsplash.com/featured?96",
    "https://source.unsplash.com/featured?95",
    "https://source.unsplash.com/featured?94",
    "https://source.unsplash.com/featured?93",
    "https://source.unsplash.com/featured?92",
    "https://source.unsplash.com/featured?91",
    "https://source.unsplash.com/featured?90",
    "https://source.unsplash.com/featured?89",
    "https://source.unsplash.com/featured?88",
    "https://source.unsplash.com/featured?81",
    "https://source.unsplash.com/featured?87",
    "https://source.unsplash.com/featured?86",
    "https://source.unsplash.com/featured?85",
    "https://source.unsplash.com/featured?84",
    "https://source.unsplash.com/featured?98",
    "https://source.unsplash.com/featured?97",
    "https://source.unsplash.com/featured?96",
    "https://source.unsplash.com/featured?95",
    "https://source.unsplash.com/featured?94",
    "https://source.unsplash.com/featured?93",
    "https://source.unsplash.com/featured?92",
    "https://source.unsplash.com/featured?91",
    "https://source.unsplash.com/featured?90",
    "https://source.unsplash.com/featured?89",
    "https://source.unsplash.com/featured?88",
    "https://source.unsplash.com/featured?81",
    "https://source.unsplash.com/featured?87",
    "https://source.unsplash.com/featured?86",
    "https://source.unsplash.com/featured?85",
    "https://source.unsplash.com/featured?84",
  ];
</script>

<div class="gallery">
  {#each images as image}
  <div class="item"><img src="{image}" /></div>
  {/each}
</div>
<style>
  .gallery {
    display: flex;
    flex-wrap: wrap;
  }

  .item {
    height: 40vh;
    flex-grow: 1;
  }
  .item:last-child {
    flex-grow: 10;
  }

  img {
    max-height: 100%;
    min-width: 100%;
    object-fit: cover;
    vertical-align: bottom;
  }

  @media (max-aspect-ratio: 1/1) {
    .item {
      height: 30vh;
    }
  }

  @media (max-height: 480px) {
    .item {
      height: 80vh;
    }
  }

  @media (max-aspect-ratio: 1/1) and (max-width: 480px) {
    .gallery {
      flex-direction: row;
    }

    .item {
      height: auto;
      width: 100%;
    }
    img {
      width: 100%;
      max-height: 75vh;
      min-width: 0;
    }
  }
</style>
