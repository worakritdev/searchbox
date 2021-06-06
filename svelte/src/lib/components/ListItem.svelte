<script>
  export let items = [];
  items = items.flat();
  function favorite(item) {
    console.log(item);
  }
  function unread(item) {
    console.log(item);
  }
</script>

<list>
  {#each items as { item }, i}
    <!-- Sliding item with text options on both sides -->
    <ion-card>
      <ion-card-header>
        <ion-card-subtitle>{item.site.split("/")[2]}🚀</ion-card-subtitle>
        <ion-card-title>
          {item.title}
        </ion-card-title>
      </ion-card-header>
      <ion-card-content>{item.description}</ion-card-content>
    </ion-card>
  {/each}
</list>
