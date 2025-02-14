<script>
  import Years from "./Years.svelte"

  export let description
  export let organization
  export let startYear
  export let endYear
  export let year

  $: years = {startYear, endYear, year}
</script>

<article>
  <span class="description certification-description">{description}</span>
  &ndash;
  <span class="organization certification-organization">{organization}</span>
  <Years {...years} />
</article>
