<script>
  import FormattedText from './FormattedText.svelte'

  export let block

  console.log({ block })

  const isLink = (section) => {
    return section[1] && section[1][0] && section[1][0][0] === 'a'
  }
</script>

{#if block.properties}
  <p>
    {#each block.properties.title as section}
      {#if isLink(section)}
        <a href="{section[1][0][1]}" target="_blank" rel="noopener">
          <FormattedText text="{section}" />
        </a>
      {:else}<FormattedText text="{section}" />{/if}
    {/each}
  </p>
{:else}
  <br />
{/if}
