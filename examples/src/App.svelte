<script context="module">
  import Notion from '../../src/Notion.svelte'
  import { fetchNotion } from '../../src/fetchNotion'
  const pageId = `a93d179a4dc74d19a1afd71818b72abd`

  fetchNotion({ id: pageId, context: this }).then((res) => console.log(res))

  const fetchImage = (async () => {
    return await fetchNotion({ id: pageId, context: this })
  })()
</script>

<svelte:head>
  <title>Blog</title>
</svelte:head>

{#await fetchImage}
  <p>...waiting</p>
{:then blocks}
  <Notion blocks="{blocks}" />
{:catch error}
  <p>An error occurred!</p>
{/await}
