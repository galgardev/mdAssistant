<!-- Sidebar.svelte -->
<script>
  import logo from "../assets/logo-dark.svg";
</script>

<dialog class="left small" id="dialog-expanded">
  <header class="fixed">
    <nav>
      <button
        class="circle extra transparent small-margin"
        data-ui="#dialog-expanded"
      >
        <i>menu</i>
      </button>
      <a href="#">
        <img src={logo} class="logo" alt="galgar.dev" draggable="false" />
      </a>
    </nav>
  </header>
  <a class="row round" data-ui="#dialog-expanded" href="#">
    <i>add</i>
    <div>New file</div>
  </a>
  <a class="row round" data-ui="#dialog-expanded" href="#">
    <i>folder</i>
    <div>Load a file</div>
  </a>
  <a class="row round" data-ui="#dialog-expanded" href="#">
    <i>save</i>
    <div>Save file</div>
  </a>
  <a class="row round" data-ui="#dialog-expanded" href="#">
    <i>print</i>
    <div>Export as PDF</div>
  </a>
  <div class="small-divider" />
  <a class="row round" data-ui="#dialog-expanded" href="#">
    <i>feed</i>
    <div>Blog</div>
  </a>
  <a class="row round" data-ui="#dialog-expanded" href="#">
    <i>info</i>
    <div>About me</div>
  </a>
  <a class="row round" data-ui="#dialog-expanded" href="#">
    <i>category</i>
    <div>Other Apps</div>
  </a>
</dialog>

<style>
  dialog {
    padding: 2.2rem 1rem;
  }
  dialog .logo {
    height: 2rem;
  }
  dialog > .row {
    padding: 0.75rem;
  }
</style>
