
<script>
  import ListItem from "$lib/components/ListItem.svelte";
  import Fuse from "fuse.js";
  import { onMount } from "svelte";
  export let blogs;
  let q = "",
    promise;

  const fuse = new Fuse(blogs, {
    keys: ["title", "article", "description", "tags"],
  });

  function searchInput(ev) {
    q = ev.target.value;
    console.log("Onsearch :", q);
    console.log(fuse,blogs);
    promise = fuse.search(q);
  }
</script>

<ion-searchbar
  placeholder="ค้นหา"
  inputmode="search"
  type="search"
  name="q"
  on:change={(ev) => {
    searchInput(ev);
  }}
  debounce="250"
  show-cancel-button="focus"
/>
{#await promise}
  <!-- optionally show something while promise is pending -->
  กำลังค้นหา
{:then data}
  {#if data}
    <ListItem items={data} />
  {/if}
{:catch error}
  <!-- optionally show something while promise was rejected -->
{/await}

