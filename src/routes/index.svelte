<script>
  // import Carousel from "../components/Carousel.svelte";
</script>

<div class="container">
  <div class="carousel">
    <div class="heading">
      <h2 class="header">Who Cares?</h2>
    </div>
    <div class="content">
      <div class="short-text">
        <p class="description">
          If human destroy the EARTH <br />
          They destroy the chance of LIFE
        </p>
        <a href="#" class="read-more">
          Read more
        </a>
      </div>
      <div class="carousel-controls">
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
      </div>
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
