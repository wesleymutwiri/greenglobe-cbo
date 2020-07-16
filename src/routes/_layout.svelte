<script>
	import Nav from '../components/Nav.svelte';
	import SideNav from '../components/SideNav.svelte';
	import ThemeContext from "../components/ThemeContext.svelte";
	export let segment;
</script>

<style>
	main {
		/* width: 100%; */
		/* margin-left: 300px; */
		background-color: var(--theme-background);
		color: var(--theme-text);
		min-height: 100vh;
		max-width: 100vw;
	}

</style>
<ThemeContext>


<main>

<Nav {segment}/>
	<slot></slot>
</main>
</ThemeContext>