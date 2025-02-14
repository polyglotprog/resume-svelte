<script>
  import Years from "./Years.svelte"

  export let description
  export let startYear
  export let endYear
  export let year

  $: years = {startYear, endYear, year}
</script>

<article class="award">
  <span class="award--description">{description.replaceAll('-', '\u2013')}</span>
  <Years {...years} />
</article>
