<script>
  import Carousel from "../components/Carousel.svelte";
</script>
<svelte:head>
	<title>Greenglobe-cbo</title>
</svelte:head>
<div class="container">
  <Carousel/>
  <div class="fill-width">
    <a class="twitter-timeline" data-align="center" data-theme="dark" data-height="1000" href="https://twitter.com/GreenGlobe_CBO?ref_src=twsrc%5Etfw">Tweets by GreenGlobe_CBO</a> 
    <a href="https://twitter.com/GreenGlobe_CBO?ref_src=twsrc%5Etfw" class="twitter-follow-button" data-size="large" data-show-count="false">Follow @GreenGlobe_CBO</a>
  </div>
</div>
<style>
.fill-width {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-items: center;
  text-align: center;
}
</style>
