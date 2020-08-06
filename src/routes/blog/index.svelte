<script>
  import { onMount } from "svelte";

  const apiUrl = process.env.SAPPER_APP_API_URL;

  let posts = [];
  onMount(async () => {
    const res = await fetch(`${apiUrl}/wp/v2/posts`);
    const json = await res.json();
    posts = json;
    console.log(posts);
  });
</script>

<ul>
  {#each posts as post}
  <li>
    <a rel="prefetch" href="blog/{post.slug}">
      {post.title.rendered}
    </a>
  </li>
  {/each}
</ul>
