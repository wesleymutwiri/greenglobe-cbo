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

<div class="container">
  <div class="waterfall">
    {#each images as image}
    <div class="item"><img src="{image}" /></div>
    {/each}
  </div>
</div>
<style>
  .container {
    display: grid;
    place-content: center;
  }
  .waterfall {
    width: 80vw;
    margin: 10rem 0;
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
    grid-gap: 1rem;
    grid-auto-flow: row dense;
    grid-auto-rows: 10vh;
  }
  .waterfall .item:nth-of-type(3n + 1) {
    grid-row: auto / span 3;
  }
  .waterfall .item:nth-of-type(3n + 2) {
    grid-row: auto / span 4;
  }
  .waterfall .item:nth-of-type(3n + 3) {
    grid-row: auto / span 5;
  }
  .waterfall .item {
    overflow: hidden;
    -webkit-transform: rotate(-7.5deg);
    transform: rotate(-7.5deg);
    /* -webkit-filter: saturate(0) contrast(10) brightness(0.2);
    filter: saturate(0) contrast(10) brightness(0.2); */
    -webkit-transition: border 0.1s, -webkit-transform 0.2s;
    transition: border 0.1s, -webkit-transform 0.2s;
    transition: transform 0.2s, border 0.1s;
    transition: transform 0.2s, border 0.1s, -webkit-transform 0.2s;
    box-sizing: border-box;
    border: 1em solid transparent;
  }
  .waterfall .item img {
    width: 100%;
    height: 100%;
    -o-object-fit: cover;
    object-fit: cover;
    -webkit-transform: rotate(15deg);
    transform: rotate(15deg);
    -webkit-transition: all 0.3s;
    transition: all 0.3s;
  }
  .waterfall .item.inbound {
    -webkit-transform: rotate(0);
    transform: rotate(0);
    -webkit-filter: none;
    filter: none;
    border-bottom: 1px solid white;
  }
  .waterfall .item.inbound img {
    -webkit-transform: rotate(0);
    transform: rotate(0);
  }
</style>
