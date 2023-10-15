<!-- Nav.svelte -->
<script>
  import logo from "../assets/logo-dark.svg";
  import Sidebar from "./Sidebar.svelte";
</script>

<nav class="top">
  <button
    class="circle extra transparent small-margin"
    data-ui="#dialog-expanded"><i>menu</i></button
  >

  <a href="https://galgar.dev">
    <img src={logo} class="logo" alt="galgar.dev" draggable="false" />
  </a>

  <div class="max" />
  <button class="transparent large circle small-margin">
    <i>light_mode</i>
  </button>
</nav>
<div class="overlay" />
<Sidebar />

<style>
  nav {
    height: auto;
    padding: 0.9rem 2rem 0.9rem 0.5rem;
  }

  nav a {
    min-width: auto;
    width: auto;
  }

  nav .logo {
    height: 2em;
    user-select: none;
  }

  @media only screen and (min-width: 993px) {
    nav {
      padding: 1rem 1rem;
    }
  }
</style>
