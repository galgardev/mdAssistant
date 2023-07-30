<!-- src\App.svelte -->
<script>
  // Import necessary libraries
  import { onMount, onDestroy } from "svelte";
  import * as monaco from "monaco-editor";
  import { marked } from "marked";

  // Initialize editor and markdown content
  let editor;
  let markdownContent = "# Hola mundo. Esto es una prueba.";

  // Monaco Editor options
  const editorOptions = {
    value: markdownContent,
    language: "markdown",
    theme: "vs-dark",
    automaticLayout: true,
  };

  // Function to render markdown to HTML
  function renderMarkdown() {
    const renderedHTML = marked(markdownContent);
    return renderedHTML;
  }

  // Lifecycle hooks to handle editor setup and destruction
  onMount(() => {
    editor = monaco.editor.create(
      document.getElementById("monacoEditor"),
      editorOptions
    );

    editor.onDidChangeModelContent(() => {
      markdownContent = editor.getValue();
    });
  });

  onDestroy(() => {
    if (editor) {
      editor.dispose();
    }
  });
</script>

<main>
  <h1>Hola mundo</h1>
  <div class="editor-container">
    <div id="monacoEditor" style="height: 400px; width: 50%;" />
    <div class="markdown-preview" style="height: 400px; width: 50%;">
      {@html renderMarkdown()}
    </div>
  </div>
</main>

<style>
  .editor-container {
    display: flex;
    gap: 10px;
  }

  .markdown-preview {
    overflow-y: auto;
    border: 1px solid #ccc;
    padding: 10px;
  }
</style>
