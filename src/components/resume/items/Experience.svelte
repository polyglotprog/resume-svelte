<script>
  import Years from "./Years.svelte"

  export let organization
  export let name
  export let location
  export let description
  export let comment
  export let startYear
  export let endYear
  export let year
  export let tasks

  $: years = {startYear, endYear, year}
</script>

<article class="experience">
  <div>
    <span class="organization">{organization || name}</span>
    {#if URL.parse(location)}
    <a class="location" href={location}>{location}</a>
    {:else}
    <span class="location">{location}</span>
    {/if}
  </div>
  <div>
    <span class="description">{description.replaceAll('-', '\u2013')}</span>
    {#if comment}
    <span class="comment">({comment})</span>
    {/if}
    <Years {...years} />
  </div>
  {#if tasks && tasks.length}
    <ul class="task-list">
      {#each tasks as task}
        <li class="task-item">{task}</li>
      {/each}
    </ul>
  {/if}
</article>
