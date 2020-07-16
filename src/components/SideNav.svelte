<script>
import ThemeToggle from './ThemeToggle.svelte';
</script>

<div class="sidebar">

<div class="profile">
<figure>
<img src="https://via.placeholder.com/150" alt="" class="profile-icon">
<figcaption>Samantha</figcaption>
<span class="email">samantha@email.com</span>
</figure>
</div>
<div class="sidebar-items">
    <a href="design" class="side-items">Design</a>
    <a href="#" class="side-items">Barbeque</a>
    <a href="#" class="side-items">Productivity</a>
    <a href="#" class="side-items">Workout</a>
    <a href="#" class="side-items">Books</a>
    <a href="#" class="side-items">Snack</a>
</div>

<div class="theme-switcher">
<ThemeToggle/>
</div>
</div>


<style>
.profile-icon {
    width: 60px;
    height: 60px;
    border-radius: 8px;
}

.sidebar-items {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;
}

.side-items {
    padding: 10px;
    text-decoration: none;
}

.sidebar {
    padding: 20px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: space-between;
    height: 100%;
    min-height: 100vh;
    font-weight: bold;
    font-size: 1.3rem;
}

figure {
    margin: 0;
}


</style>