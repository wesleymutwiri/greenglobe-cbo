<script>
  import Carousel from "../components/Carousel.svelte";
  import { onMount } from 'svelte';

  onMount(() => {
    if (window.netlifyIdentity) {
      window.netlifyIdentity.on("init", user => {
        if (!user) {
          window.netlifyIdentity.on("login", () => {
            document.location.href = "/admin/";
          });
        }
      });
    }
  });
</script>
<svelte:head>
  <title>Greenglobe-cbo</title>
  <script src="https://identity.netlify.com/v1/netlify-identity-widget.js"></script>
</svelte:head>
<div class="container">
  <Carousel />
  <h3>About Us</h3>
  <div class="about">
    <div class="image">
      <img src="https://res.cloudinary.com/wesleymochiemo/image/upload/v1598892035/DSC_8917_rc1wro.jpg"
        alt="GreenGlobe members during a River Clean Up">
    </div>
    <div class="about-text">
      Green Globe CBO is a grass-root Not-for-profit Community Based Organization
      (CBO) based in Nairobi, Kenya. We aim to have clean and sustainable
      communities around Nairobi City. Green Globe CBO is committed to educate
      communities on proper waste disposal methods with specific emphasis on
      plastic waste.
    </div>
  </div>
  <h3>Currently Ongoing Projects</h3>
  <div class="projects">
    <div class="project">
      <div class="project-text">

      </div>
      <div class="project-image">
        <img src="" alt="">
      </div>
    </div>
    <div class="project">

    </div>
    <div class="project">

    </div>
  </div>
</div>
<div class="fill-width">
  <a class="twitter-timeline" data-align="center" data-theme="dark" data-height="1000"
    href="https://twitter.com/GreenGlobe_CBO?ref_src=twsrc%5Etfw">Tweets by GreenGlobe_CBO</a>
  <a href="https://twitter.com/GreenGlobe_CBO?ref_src=twsrc%5Etfw" class="twitter-follow-button" data-size="large"
    data-show-count="false">Follow @GreenGlobe_CBO</a>
</div>
<style>
  h3 {
    text-align: center;
    padding: 20px;
    margin: 30px;
    font-size: 2rem;
  }

  .fill-width {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-items: center;
    text-align: center;
  }

  .about {
    display: flex;
    justify-items: space-between;
    padding: 20px;
    margin: auto;
  }

  .about-text {
    display: flex;
    justify-items: center;
    align-items: center;
    max-width: 800px;
    margin: auto;
    line-height: 1.5;
    font-size: 1.2rem;
    width: 50%;
  }

  .image {
    width: 50%;
  }

  .image img {
    width: 100%;
    padding: 20px;
  }

  @media screen and (max-width: 850px) {
    .about {
      flex-direction: column;
    }

    .image {
      width: 100%;
    }

    .about-text {
      width: 100%;
      max-width: 100%;
      padding: 20px;
    }
  }
</style>