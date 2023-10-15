<!-- src/components/Render.svelte -->
<script>
  export let renderedHTML = "";
  import "../render.css";
</script>

<div id="render">
  {@html renderedHTML}
</div>
