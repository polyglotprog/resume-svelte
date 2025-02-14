<script>
  export let startYear
  export let endYear
  export let year
</script>

<span class="years">
  {#if startYear && endYear}
    {startYear}&ndash;{endYear}
  {:else if year}
    {year}
  {/if}
</span>
