<script>
  export let items;
  console.log(items)
</script>

{#each items as item}
  {JSON.stringify(item)}
{/each}
