<script context="module">
  export async function load({ page, fetch }) {
    const url = `http://localhost:1337/pages`;
    const res = await fetch(url);

    const blogs = await res.json();

    return {
      props: {
        blogs: blogs,
      },
    };
  }
</script>

<script>
  import Search from "$lib/components/Search.svelte";
  import { onMount } from "svelte";

  export let blogs;
</script>

{#if blogs}
  <Search {blogs} />
{/if}
