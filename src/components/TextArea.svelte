<script>
  import MarkdownIt from "markdown-it";

  const md = new MarkdownIt();

  let markdownText = "# Hello, Markdown!";
  let htmlOutput = "";

  function updateHTML() {
    htmlOutput = md.render(markdownText);
  }

  function handleKeyup() {
    updateHTML();
  }

  updateHTML();
</script>

<div>
  <textarea bind:value={markdownText} on:keyup={handleKeyup}></textarea>
  <div class="markdown-body">
    {@html htmlOutput}
  </div>
</div>

<style>
  textarea {
    width: 100%;
    height: 150px;
    margin-bottom: 10px;
    font-family: monospace;
    font-size: 1rem;
  }

  .markdown-body {
    border: 1px solid #ccc;
    padding: 10px;
    border-radius: 5px;
    background-color: #f9f9f9;
  }
</style>
