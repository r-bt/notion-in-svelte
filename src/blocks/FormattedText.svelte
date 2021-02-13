<script>
  export let text

  let classes = []
  if (text[1]) {
    classes = text[1].map((attr) => attr[0])
  }

  console.log(classes)
</script>

<style>
  span {
    white-space: pre-line;
  }
  .bold {
    font-weight: bold;
  }
  .italic {
    font-style: italic;
  }
  .underline {
    text-decoration: underline;
  }
  .strikethrough {
    text-decoration: line-through;
  }
  .underline.strikethrough {
    text-decoration: underline line-through;
  }
  .code {
    background-color: rgb(63, 63, 63);
    padding: 5px 8px;
    border-radius: 5px;
    color: white;
  }
</style>

<span
  class:bold="{classes.includes('b')}"
  class:italic="{classes.includes('i')}"
  class:code="{classes.includes('c')}"
  class:underline="{classes.includes('u')}"
  class:strikethrough="{classes.includes('s')}"
>
  {text[0]}
</span>
