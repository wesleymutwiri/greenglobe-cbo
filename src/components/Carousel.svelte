<script>
  import { fade } from "svelte/transition";

  const carouselPhotos = [
    "globe.svg",
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
{#each [carouselPhotos[currentCarouselIndex]] as photo (currentCarouselIndex)}
<div class="carousel" style="background-image: url({photo})" transition:fade>
  <div class="heading">Who cares</div>
  <div class="content">
    <a href="#" class="read-more">Read More</a>
    <div class="carousel-controls">
      <span on:click="{previous}" class="round-button previous">
        <svg
          viewBox="0 0 24 24"
          width="24"
          height="24"
          stroke="currentColor"
          stroke-width="2"
          fill="none"
          stroke-linecap="round"
          stroke-linejoin="round"
          class="css-i6dzq1"
        >
          <polyline points="15 18 9 12 15 6"></polyline>
        </svg>
      </span>
      <span on:click="{next}" class="round-button next">
        <svg
          viewBox="0 0 24 24"
          width="24"
          height="24"
          stroke="currentColor"
          stroke-width="2"
          fill="none"
          stroke-linecap="round"
          stroke-linejoin="round"
          class="css-i6dzq1"
        >
          <polyline points="9 18 15 12 9 6"></polyline>
        </svg>
      </span>
    </div>
  </div>
</div>
{/each}

<style>
  .carousel {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    height: 92vh;
    background-size: 40% 90%;
    background-repeat: no-repeat;
    background-position: center;
    background-attachment: fixed;
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
    font-weight: 900;
  }
  .read-more:hover {
    color: #fed121;
  }

  .carousel-controls {
    margin-right: 2rem;
  }

  .round-button {
    border-radius: 50%;
    background: var(--theme-svg);
    padding: 10px;
    text-align: center;
    height: max-content;
    padding-top: 22px;
    color: #fff;
    cursor: pointer;
  }
  @media screen and (max-width: 600px) {
    .heading {
      font-size: 4rem;
    }
  }
</style>
