<script>
import { setContext, onMount } from "svelte";
  import { writable } from "svelte/store";
  import { presets } from "./themes/themes.js";
  // expose props for customization and set default values
  export let themes = [...presets];
  // set state of current theme's name
  let _current = themes[0].name;

  // utility to get current theme from name
  const getCurrentTheme = name => themes.find(h => h.name === name);
  // set up Theme store, holding current theme object
  const Theme = writable(getCurrentTheme(_current));

  setContext("theme", {
    // providing Theme store through context makes store readonly
    theme: Theme,
    toggle: () => {
      // update internal state
      let _currentIndex = themes.findIndex(h => h.name === _current);
      _current =
        themes[_currentIndex === themes.length - 1 ? 0 : (_currentIndex += 1)]
          .name;
      // update Theme store
      Theme.update(t => ({ ...t, ...getCurrentTheme(_current) }));
      setRootColors(getCurrentTheme(_current));
    }
  });

  onMount(() => {
    // set CSS vars on mount
    setRootColors(getCurrentTheme(_current));
  });
  
  let themeContainer;
  // sets CSS vars for easy use in components
  // ex: var(--theme-background)
  const setRootColors = theme => {
    for (let [prop, color] of Object.entries(theme.colors)) {
      let varString = `--theme-${prop}`;
      themeContainer.style.setProperty(varString, color);
    }
    themeContainer.style.setProperty("--theme-name", theme.name);
  };
</script>
<div class="container" bind:this={themeContainer}>
<slot></slot>
</div>

<style>
.container {
    width: 100%;
    height: 100%;
    min-width: 100vw;
    min-height: 100vh;
	background-color: var(--theme-background);

}
</style>