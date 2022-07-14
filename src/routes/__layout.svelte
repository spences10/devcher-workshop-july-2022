<script>
  import Nav from '$lib/components/nav.svelte'
  import { onMount } from 'svelte'
  import { themeChange } from 'theme-change'
  import '../app.css'

  onMount(() => {
    themeChange(false)
  })
</script>

<Nav />

<main class="container max-w-3xl mx-auto px-4">
  <slot />
</main>
