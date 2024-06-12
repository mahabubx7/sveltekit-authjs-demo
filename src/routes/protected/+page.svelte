<script lang="ts">
  import { page } from "$app/stores"
</script>

{#if $page.data.session}
  <h1>Protected page</h1>
  <p>
    This is a protected content. You can access this content because you are
    signed in.
  </p>
  <p>Session expiry: {$page.data.session?.expires}</p>
  <code>
    <pre>{JSON.stringify($page.data.session, null, 2)}</pre>
  </code>
{:else}
  <h1>Access Denied</h1>
{/if}
