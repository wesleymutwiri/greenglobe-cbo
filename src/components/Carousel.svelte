<script>
  import { fade } from "svelte/transition";

  const carouselPhotos = [
    "https://picsum.photos/300/200?random=1",
    "https://picsum.photos/300/200?random=2",
    "https://picsum.photos/300/200?random=3",
    "https://picsum.photos/300/200?random=4",
  ];

  let currentCarouselIndex = 0;
  const next = () =>
    (currentCarouselIndex = (currentCarouselIndex + 1) % carouselPhotos.length);
  const previous = () =>
    (currentCarouselIndex =
      currentCarouselIndex != 0
        ? currentCarouselIndex - 1
        : carouselPhotos.length - 1);
</script>
<div class="carousel">
  <div class="heading">
    Who cares
  </div>
  {#each [carouselPhotos[currentCarouselIndex]] as photo (currentCarouselIndex)}
  <img transition:fade src="{photo}" alt="" />
  {/each}
  <div class="content">
    <div class="read-more">
      <a href="#">Read More</a>
    </div>
    <div class="carousel-controls">
      <button on:click="{next}">Next</button>
      <button on:click="{previous}">Previous</button>
    </div>
  </div>
</div>

<style>
  .carousel {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    height: 90vh;
  }
  .heading {
    font-size: 6rem;
    font-weight: 900;
    padding-left: 2rem;
  }

  .content {
    padding-left: 2rem;
    font-weight: 900;
    display: flex;
    justify-content: space-between;
  }
  .read-more {
    text-decoration: none;
    color: #fed121;
    text-transform: uppercase;
    margin-top: 1.5rem;
    display: block;
  }
  .read-more:hover {
    color: #fed121;
  }

  .carousel-controls {
    margin-right: 2rem;
  }

  @media screen and (max-width: 600px) {
    .heading {
      font-size: 4rem;
    }
  }
</style>
