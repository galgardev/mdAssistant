<!-- Nav.svelte -->
<script>
  import logo from "../assets/logo-dark.svg";
  import Sidebar from "./Sidebar.svelte";
</script>

<nav class="top">
  <button
    class="circle extra transparent s m l small-margin"
    data-ui="#dialog-expanded"><i>menu</i></button
  >

  <a href="https://galgar.dev">
    <img src={logo} class="logo" alt="galgar.dev" draggable="false" />
  </a>

  <div class="max" />
  <button class="transparent extra circle">
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
    margin-right: 0.8rem !important;
    min-width: auto;
    width: auto;
  }

  nav a:hover {
    text-decoration: underline;
  }

  nav .logo {
    height: 2em;
    user-select: none;
  }

  @media only screen and (min-width: 993px) {
    nav {
      padding: 1.4rem 2rem;
    }
  }

  @media only screen and (max-width: 992px) {
    .nav-link {
      display: none !important;
    }
  }
</style>
