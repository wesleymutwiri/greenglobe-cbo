<script>
  import { getContext } from "svelte";
  const { theme, toggle } = getContext("theme");
</script>

<label class="switch">
  <input type="checkbox" class="switch-input" id="time" on:click="{toggle}" />
  <label for="time">Night</label>
</label>
<!-- <button on:click={toggle}>{$theme.name}</button> -->

<style>
  #btn--yp {
    box-sizing: content-box;
    position: fixed;
    z-index: 9;
    bottom: 1em;
    right: 1em;
    border: solid 1em transparent;
    width: 4.625em;
    height: 3.25em;
    background: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/2017/icon-yp.svg)
      50% / cover content-box;
    font: 16px/ 1.25 trebuchet ms, sans-serif;
    text-indent: 200vw;
    text-shadow: none;
    filter: grayscale(1) drop-shadow(0 0 1px #e8e0e0);
    transition: 0.5s;
    white-space: nowrap;
  }
  #btn--yp:before {
    box-sizing: inherit;
    position: absolute;
    left: 0;
    bottom: 100%;
    margin: 2em -0.5em;
    padding: 0.5em;
    width: 100%;
    border-radius: 5px;
    background: #e8e0e0;
    color: #000;
    text-align: center;
    text-decoration: none;
    text-indent: 0vw;
    white-space: normal;
    animation: float 1s ease-in-out infinite alternate;
    content: attr(data-txt);
  }
  #btn--yp:hover,
  #btn--yp:focus {
    outline: none;
    filter: grayscale(0) drop-shadow(0 0 1px crimson);
  }

  @keyframes float {
    to {
      transform: translateY(0.75em);
    }
  }

  #time {
    position: absolute;
    right: 100vw;
  }
  #time + label {
    --i: 0;
    --j: calc(1 - var(--i));
    display: grid;
    grid-gap: 0.5em 0.5em;
    overflow: hidden;
    padding: 0.5em;
    height: 2.5em;
    border-radius: 1.75em;
    background: hsl(199, 98%, calc(var(--j) * 48%));
    color: transparent;
    user-select: none;
    transition: 0.3s;
    cursor: pointer;
  }
  #time + label:before,
  #time + label:after {
    width: 2em;
    height: 2em;
    transition: inherit;
    content: "";
  }
  #time + label:before {
    transform-origin: 20% 20%;
    transform: translate(calc(var(--i) * (100% + 0.25em)))
      scale(calc(1 - var(--i) * 0.7));
    background: yellow;
    --poly: polygon(
      44.13371% 12.96169%,
      50% 0%,
      55.86629% 12.96169%,
      59.70571% 13.77778%,
      63.4388% 14.99073%,
      67.02464% 16.58726%,
      79.38926% 9.54915%,
      76.5165% 23.4835%,
      79.14297% 26.40049%,
      81.45015% 29.57604%,
      83.41274% 32.97536%,
      97.55283% 34.54915%,
      87.03831% 44.13371%,
      87.44861% 48.0374%,
      87.44861% 51.9626%,
      87.03831% 55.86629%,
      97.55283% 65.45085%,
      83.41274% 67.02464%,
      81.45015% 70.42396%,
      79.14297% 73.59951%,
      76.5165% 76.5165%,
      79.38926% 90.45085%,
      67.02464% 83.41274%,
      63.4388% 85.00927%,
      59.70571% 86.22222%,
      55.86629% 87.03831%,
      50% 100%,
      44.13371% 87.03831%,
      40.29429% 86.22222%,
      36.5612% 85.00927%,
      32.97536% 83.41274%,
      20.61074% 90.45085%,
      23.4835% 76.5165%,
      20.85703% 73.59951%,
      18.54985% 70.42396%,
      16.58726% 67.02464%,
      2.44717% 65.45085%,
      12.96169% 55.86629%,
      12.55139% 51.9626%,
      12.55139% 48.0374%,
      12.96169% 44.13371%,
      2.44717% 34.54915%,
      16.58726% 32.97536%,
      18.54985% 29.57604%,
      20.85703% 26.40049%,
      23.4835% 23.4835%,
      20.61074% 9.54915%,
      32.97536% 16.58726%,
      36.5612% 14.99073%,
      40.29429% 13.77778%
    );
    -webkit-clip-path: var(--poly);
    clip-path: var(--poly);
  }
  #time + label:after {
    grid-column: 2;
    border-radius: 50%;
    transform: translatey(calc(var(--i) * (-100% - 0.5em)));
    background: radial-gradient(
      circle at 19% 19%,
      rgba(0, 0, 0, 0) 41%,
      #ffffff 43%
    );
  }
  #time:checked + label {
    --i: 1;
  }
</style>
