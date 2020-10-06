<script context="module">
  export async function preload({ params, query }) {
    const res = await this.fetch(`_posts/${params.slug}.md`);
    if (res.status === 200) {
      return { postMd: await res.text() };
    } else {
      this.error(res.status, data.message);
    }
  }
</script>

<script>
  import fm from "front-matter";
  import MarkdownIt from "markdown-it";
  export let postMd;
  const md = new MarkdownIt();
  $: frontMatter = fm(postMd);
  $: post = {
    ...frontMatter.attributes,
    html: md.render(frontMatter.body),
  };
  // console.log(post);
</script>

<div class="content">{@html post.html}</div>

<style></style>
