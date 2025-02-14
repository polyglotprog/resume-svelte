<script>
  export let name
</script>

<h1 class="name">
  {#if typeof name === 'string'}
    {name}
  {:else}
    {#if name.first}
      <span class="first-name">{name.first}</span>
    {/if}
    {#if name.middle}
      <span class="middle-name">{name.middle}</span>
    {/if}
    {#if name.first}
      <span class="last-name">{name.last}</span>
    {/if}
  {/if}
</h1>
