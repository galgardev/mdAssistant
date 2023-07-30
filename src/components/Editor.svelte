<script>
  import { onMount } from "svelte";
  import * as monaco from "monaco-editor";
  import { marked } from "marked";
  import Render from "./Render.svelte";
  import "../editor.css";

  let editorInstance;
  let editorContent = "";
  let renderedHTML = "";

  // Opciones del editor
  const editorOptions = {
    language: "markdown",
    theme: "vs-dark",
    automaticLayout: true,
    wordWrap: "on",
    fontFamily: "Courier New",
    fontSize: 16,
    lineNumbers: "on",
    folding: false,
    minimap: {
      enabled: false,
    },
    scrollbar: {
      vertical: "visible",
      horizontal: "hidden",
      verticalHasArrows: false,
      horizontalHasArrows: false,
      verticalScrollbarSize: 14,
    },
  };

  // Obtiene la plantilla de Markdown e inicializa el editor
  async function fetchMarkdownTemplate() {
    const response = await fetch("src/assets/markdown-example.md");
    editorContent = await response.text();
    editorOptions.value = editorContent;
    updateRenderedHTML();
  }

  // Configura el editor
  function initializeEditor() {
    editorInstance = monaco.editor.create(
      document.getElementById("code-editor"),
      // @ts-ignore
      editorOptions
    );

    editorInstance.onDidChangeModelContent(
      // Detecta cambios en el editor y llama a la función que actualiza el renderizado
      function onEditorContentChange() {
        editorContent = editorInstance.getValue();
        updateRenderedHTML();
      }
    );
  }

  // Actualiza el HTML renderizado
  function updateRenderedHTML() {
    renderedHTML = marked(editorContent);
  }

  // Se ejecuta al montar el componente para obtener la plantilla e inicializar el editor
  function onMountHandler() {
    fetchMarkdownTemplate().then(initializeEditor);
  }

  onMount(onMountHandler);
</script>

<div class="grid">
  <div class="m12 l6">
    <div id="code-editor" />
  </div>
  <div class="m12 l6">
    <Render {renderedHTML} />
  </div>
</div>
