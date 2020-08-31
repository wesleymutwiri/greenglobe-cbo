<script>
	import SearchButton from './SearchButton.svelte';
	// import ThemeToggle from './ThemeToggle.svelte';
	import { onMount } from "svelte";
	export let segment;

	let showMobileMenu = false; 

	const handleMobileIconClick = () => (showMobileMenu =! showMobileMenu)

	const mediaQueryHandler = e => {
		if (!e.matches) {
			showMobileMenu = false;
		}
	};

onMount(() => {
	const mediaListener = window.matchMedia("(max-width: 1260px)")
	mediaListener.addListener(mediaQueryHandler);
})
</script>


<style>
	nav {
		/* grid-template-areas: "logo navbar-items search"; */
		border-bottom: 1px solid rgba(255,62,0,0.1);
		font-weight: 300;
		height: 65px;
		margin-bottom: 12px;
	}
	.nav-elements {
		display: flex;
		width: 100%;
		padding: 0.5rem 1rem;
		justify-content: space-between;
		align-items: center;
	}

	.mobile-icon {
		width: 25px;
		height: 25px;
		position: relative;
		cursor: pointer;
		display: none;
		margin-top: 15px;
		margin-left: 15px;
	}
	.mobile-icon:after,
  .mobile-icon:before,
  .middle-line {
    content: "";
    position: absolute;
    width: 100%;
    height: 2px;
    transition: all 0.4s;
    transform-origin: center;
	background-color: var(--theme-text);

  }

  .mobile-icon:before,
  .middle-line {
    top: 0;
  }

  .mobile-icon:after,
  .middle-line {
    bottom: 0;
  }

  .mobile-icon:before {
    width: 66%;
  }

  .mobile-icon:after {
    width: 33%;
  }

  .middle-line {
    margin: auto;
  }

  .mobile-icon:hover:before,
  .mobile-icon:hover:after,
  .mobile-icon.active:before,
  .mobile-icon.active:after,
  .mobile-icon.active .middle-line {
    width: 100%;
  }

  .mobile-icon.active:before,
  .mobile-icon.active:after {
    top: 50%;
    transform: rotate(-45deg);
  }

  .mobile-icon.active .middle-line {
    transform: rotate(45deg);
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

	@media screen and (max-width: 1260px){
		.nav-elements{
			display: none;
			width: 100%;
			justify-content: space-between;
			margin: 0;
			padding: 0 40px;
			
		}
		.nav-elements.mobile {
			display: flex;
			flex-direction: column;
			height: 100vh;
			background-color: var(--theme-text);
			color: var(--theme-background);
			position: fixed;
			justify-content: space-around;
			align-items: center;
		}
		ul {
			display: flex;
			flex-direction: column;
		}
		/* .search {
			display: flex;
			flex-direction: column;
		} */
		.mobile-icon{
			display: inline-flex;
		}

	}
</style>

<nav>
<div on:click={handleMobileIconClick} class={`mobile-icon${showMobileMenu ? ' active' : ''}`}>
	<div class="middle-line"></div>
</div>
	<div class={`nav-elements${showMobileMenu ? ' mobile' : ''}`}>
	
	<div class="logo" on:click={handleMobileIconClick} >
		<a href="/">
			<img src="https://via.placeholder.com/40" alt="">
		</a>
	</div>
	<ul on:click={handleMobileIconClick} >
		<li><a aria-current="{segment === 'about' ? 'page' : undefined}" href="about">about</a></li>
		
		<!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
			the blog data when we hover over the link or tap it on a touchscreen -->
			<li><a rel=prefetch aria-current="{segment === 'blog' ? 'page' : undefined}" href="blog">blog</a></li>
			<li><a  aria-current="{segment === 'gallery' ? 'page' : undefined}" href="gallery">Gallery</a></li>
			<li><a  aria-current="{segment === 'news' ? 'page' : undefined}" href="news">News And Events</a></li>

			<li><a  aria-current="{segment === 'contact' ? 'page' : undefined}" href="contact">Contact us</a></li>


	</ul>
	<div class="search">
	<SearchButton/>
</div>
</div>
</nav>
