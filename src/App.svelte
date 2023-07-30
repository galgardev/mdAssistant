<script>
  import { onMount } from "svelte";
  import * as monaco from "monaco-editor";
  import { marked } from "marked";

  // Initialize editor and markdown content
  let editor;
  let editorContent = "# Hola mundo.";

  // Monaco Editor options
  const editorOptions = {
    value: editorContent,
    language: "markdown",
    theme: "vs-dark",
    automaticLayout: true,
  };

  // Function to render markdown to HTML
  let renderedHTML = marked(editorContent);

  function updatePreview() {
    renderedHTML = marked(editorContent);
  }

  // Hook to handle editor setup and changes
  onMount(() => {
    editor = monaco.editor.create(
      document.getElementById("code-editor"),
      editorOptions
    );

    editor.onDidChangeModelContent(() => {
      editorContent = editor.getValue();
      updatePreview();
    });
  });
</script>

<main>
  <div id="code-editor" style="height: 400px; width: 50%;" />
  <div id="previewer" style="height: 400px; width: 50%;">
    {@html renderedHTML}
  </div>
</main>

<style>
</style>
