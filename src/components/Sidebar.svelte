<!-- Sidebar.svelte -->
<script>
  import logo from "../assets/logo-dark.svg";
</script>

<dialog class="left small" id="dialog-expanded">
  <header class="fixed">
    <nav>
      <button class="transparent circle extra" data-ui="#dialog-expanded">
        <i>menu</i>
      </button>
      <a href="#">
        <img src={logo} class="logo" alt="galgar.dev" draggable="false" />
      </a>
    </nav>
  </header>
  <a class="row round" data-ui="#dialog-expanded" href="#">
    <i>feed</i>
    <div>Blog</div>
  </a>
  <!-- <div class="small-divider"></div> -->
</dialog>

<style>
  dialog {
    padding: 2.2rem 1rem;
  }
  dialog .logo {
    height: 2rem;
  }
</style>
