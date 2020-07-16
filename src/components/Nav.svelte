<script>
	import SearchButton from './SearchButton.svelte';
	import ThemeToggle from './ThemeToggle.svelte';

	export let segment;
</script>

<style>
	nav {
		display: flex;
		/* grid-template-areas: "logo navbar-items search"; */
		border-bottom: 1px solid rgba(255,62,0,0.1);
		font-weight: 300;
		padding: 0.5rem 1rem;
		justify-content: space-between;
		align-items: center;
	}

	ul {
		margin: 0;
		padding: 0;
		/* grid-area: navbar-items; */
	}

	.search{
		/* grid-area: search; */
		display: flex;
		
	}
	/* clearfix */
	ul::after {
		content: '';
		display: block;
		clear: both;
	}

	li {
		display: block;
		float: left;
		padding: 0 4rem;
	}

	[aria-current] {
		position: relative;
		display: inline-block;
	}

	[aria-current]::after {
		position: absolute;
		content: '';
		width: calc(99% - 1em);
		height: 2px;
		background-color: #fed121;
		display: block;
		bottom: 10px;
	}

	a {
		text-decoration: none;
		padding: 1rem 0.5rem;
		display: block;
		text-transform: capitalize;
	}
</style>

<nav>
	<div class="logo">
	<img src="https://via.placeholder.com/40" alt="">
	</div>
	<ul>
		<li><a aria-current="{segment === undefined ? 'page' : undefined}" href=".">home</a></li>
		<li><a aria-current="{segment === 'about' ? 'page' : undefined}" href="about">about</a></li>
		
		<!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
			the blog data when we hover over the link or tap it on a touchscreen -->
			<li><a rel=prefetch aria-current="{segment === 'blog' ? 'page' : undefined}" href="blog">blog</a></li>
			<li><a  aria-current="{segment === 'gallery' ? 'page' : undefined}" href="gallery">Gallery</a></li>
			<li><a  aria-current="{segment === 'contact' ? 'page' : undefined}" href="contact">Contact us</a></li>


	</ul>
	<div class="search">
	<SearchButton/>
	<ThemeToggle/>
</div>
</nav>
