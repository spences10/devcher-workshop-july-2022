<script context="module">
  import { client } from '$lib/graphql/graphql-clinet'
  import { gql } from 'graphql-request'

  /** @type {import('@sveltejs/kit').Load} */
  export const load = async () => {
    const query = gql`
      query AllPosts {
        posts {
          title
          slug
          date
          excerpt
          tags
          coverImage {
            url
          }
        }
      }
    `
    const { posts } = await client.request(query)

    return {
      props: { posts },
    }
  }
</script>

<script>
  import PostCard from '$lib/components/post-card.svelte'

  /** @type {any} */
  export let posts
</script>

{#each posts as post}
  <PostCard {post} />
{/each}
