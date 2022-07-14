<script context="module">
  import { client } from '$lib/graphql/graphql-client'
  import { getAllPages } from '$lib/graphql/graphql-queries'
  import { onMount } from 'svelte'
  import { themeChange } from 'theme-change'
  import '../app.css'

  /** @type {import('@sveltejs/kit').Load} */
  export const load = async () => {
    const { pages } = await client.request(getAllPages)

    return {
      props: {
        pages,
      },
    }
  }
</script>

<script>
import Nav from '$lib/components/nav.svelte';

  /** @type {any} */
  export let pages

  onMount(() => {
    themeChange(false)
  })
</script>

<Nav {pages} />
<main class="container max-w-3xl mx-auto px-4">
  <slot />
</main>