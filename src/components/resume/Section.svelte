<script>
  import Experience from "./items/Experience.svelte"
  import Skill from "./items/Skill.svelte"

  export let heading
  export let items
  export let type

  const types = {
    Experience,
    Skill
  }

  $: component = types[type]
  $: sectionClass = heading.toLowerCase()
  $: listClass = `${type.toLowerCase()}-list`
  $: itemClass = `${type.toLowerCase()}-item`
</script>

<section class={sectionClass}>
  <h3>{heading}</h3>
  {#if items && items.length}
    <ul class={listClass}>
      {#if typeof items[0] === 'string'}
        <!-- List of strings -->
        {#each items as item}
          <li class={itemClass}>{item}</li>
        {/each}
      {:else}
        <!-- List of objects -->
        {#each items as item}
          <li class={itemClass}>
            <svelte:component
              this={component}
              {...item}
            />
          </li>
        {/each}
      {/if}
    </ul>
  {:else}
    <!-- Section is empty -->
    <p class="empty">THIS SECTION IS EMPTY</p>
  {/if}
</section>
