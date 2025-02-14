<script>
  import Contact from './Contact.svelte'
  import Footer from './Footer.svelte'
  import Header from './Header.svelte'
  import Name from './Name.svelte'
  import Section from './Section.svelte'
  import Summary from './Summary.svelte'

  export let name
  export let contact
  export let sections
  export let summary
</script>

<div class="resume">
  <!-- Header -->
  <Header>
    <Name    slot="name"    name={name} />
    <Contact slot="contact" {...contact} />
  </Header>
  <!-- Summary -->
  <Summary {...summary} />
  <!-- Sections -->
  {#each sections as section}
    <Section {...section} />
  {/each}
  <!-- Footer -->
  <Footer />
</div>
