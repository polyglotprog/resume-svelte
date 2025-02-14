<script>
  export let address
  export let phone
  export let email
  export let website
</script>

<div class="contact">
  <ul class="contact-list">
    {#if address}
      <li class="contact-item">
        <address>
          {address}
        </address>
      </li>
    {/if}
    {#if phone}
      <li class="contact-item">
        <a href="phone:{phone}">
          {phone}
        </a>
      </li>
    {/if}
    {#if email}
      <li class="contact-item">
        <a href="mailto:{email}">
          {email}
        </a>
      </li>
    {/if}
    {#if website}
      <li class="contact-item">
        <a href="https://{website}">
          {website}
        </a>
      </li>
    {/if}
  </ul>
</div>
