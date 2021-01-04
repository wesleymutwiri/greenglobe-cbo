<script>
  import { fade } from "svelte/transition";

  const carouselPhotos = ["globe.svg", "globe.svg"];

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
  <div class="carousel-content">
    <div class="heading">Who Cares?</div>
    <div class="content">
      <p>If humans destroy the EARTH</p>
      <p>They Destroy the chance of LIFE</p>
      <a href="#" class="read-more">Read More</a>
    </div>
  </div>
  <div class="carousel-displays">
    <div class="next-preview">
      <h5>Up Next</h5>
      <div class="small-container">

      
      <!-- Arrow button  -->
      <svg
        viewBox="0 0 24 24"
        width="70"
        height="24"
        stroke="currentColor"
        stroke-width="2"
        fill="none"
        stroke-linecap="round"
        stroke-linejoin="round"
        class="css-i6dzq1"
      >
        <line x1="-100" y1="12" x2="19" y2="12"></line>
        <polyline points="12 5 19 12 12 19"></polyline>
      </svg>
      <!-- end of arrow button  -->
      <h3>Contributions</h3>
      <p>Small Ideas</p>
      </div>
    </div>
    <div class="progress-controls">
      <div class="progress">
        {((currentCarouselIndex + 1).toString().length < 2) ? "0" + (currentCarouselIndex + 1) : currentCarouselIndex}
        <progress value={(currentCarouselIndex +1) / (carouselPhotos.length)} class="progress-bar"></progress>
        {((carouselPhotos.length).toString().length < 2) ? "0" + (carouselPhotos.length) : (carouselPhotos.length)}
      </div>
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
</div>
{/each}

<style>
  .carousel {
    display: flex;
    justify-content: space-between;
    height: 80vh;
    background-size: 60% 90%;
    background-repeat: no-repeat;
    background-position: center;
    background-attachment: fixed;
    position: relative;
  }

  .carousel-content {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    height: 80vh;
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
    flex-direction: column;
  }
  .read-more {
    text-decoration: none;
    color: #0cf913;
    text-transform: uppercase;
    margin-top: 1.5rem;
    display: block;
    font-weight: 900;
  }
  .read-more:hover {
    color: #fed121;
  }

  .carousel-displays {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
  }

  /* .carousel-controls {
    position: absolute;
    top: 90%;
    left: 90%;
    display: flex;
  } */

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

  .next-preview {
    background-color: #0000002c;
    backdrop-filter: blur(340px);
    border-radius: 10px;
    border-top-left-radius: 80px;
    height: 300px;
    width: 340px;
    display: flex;
    justify-content: space-between;
    flex-direction: column;
    padding: 60px;
    border: solid 2px transparent;
    background-clip: padding-box;
    opacity: 0.8;
  }

  .next-preview h5 {
    font-weight: bolder;
    text-transform: uppercase;
    color: #0cf913;
  }

  .next-preview p {
    color: #a7a7a7;
  }

  .next-preview h3 {
    font-weight: 900;
    text-transform: uppercase;
  }
  .progress-controls {
    display: flex;
    justify-content: space-between;
    padding: 20px;
  }
  .progress-bar {
    width: 100px;
    color: #0cf913;
    height: 10px;
    margin: 10px;
  }
  progress[value] {
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    border: none;
    background: #6b6b6b;
  }

  progress[value]::-moz-progress-bar { 
    background: #0cf913;
    border-radius: 2px; 
    background-size: 35px 20px, 100% 100%, 100% 100%; 
  }

  progress[value]::-webkit-progress-bar {
    background-color: #eee;
    border-radius: 2px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.25) inset;
  }
  progress[value]::-webkit-progress-value {
    background: #0cf913;
    border-radius: 2px; 
    background-size: 35px 20px, 100% 100%, 100% 100%;
  }

  .progress {
    display: flex;
    align-items: center;
  }
  .small-container * {
    padding: 5px;
  }
  @media screen and (max-width: 600px) {
    .heading {
      font-size: 4rem;
    }
    .carousel {
      background-size: 100% 40%;
      height: 80vh;
      flex-direction: column;
    }
    .carousel::before{
      content: "";
      position: absolute;
      top: 0px;
      left: 0px;
      right: 0px;
      bottom: 0px;
      background-color: rgba(0, 0, 0, 0.507);
      z-index: 1;
    }
    .carousel-controls {
      left: 75%;
    }
    .carousel-content {
      z-index: 2;
    }
    .carousel-displays {
      z-index: 2;
    }
    .next-preview {
      display: none;
    }

  }
  @media screen and (max-width: 1090px) {
    .carousel {
      background-size: 100% 40%;
      justify-content: space-between;
      height: 80vh;
    }
    .carousel-controls {
      left: 75%;
    }
  }
</style>
