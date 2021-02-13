<script>
  export let code
  export let lang

  import Prism from 'prismjs'

  console.log(Prism.languages)

  const html = Prism.highlight(code, Prism.languages[lang], lang)
</script>

<pre
  class="language-{lang}">
  <code class="language-{lang}">{@html html}</code>
</pre>
