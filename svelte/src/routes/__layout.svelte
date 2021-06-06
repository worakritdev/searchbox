<script>
  export let routes = [
    { name: "Home", icon: "home", path: "/" },
    { name: "Information", icon: "information", path: "/about" },
    { name: "User", icon: "person", path: "/user" },
  ];
</script>

<!-- markup (zero or more items) goes here -->
<body>
  <ion-split-pane content-id="main" when="md">
    <ion-menu
      content-id="main"
      side="start"
      type="overlay"
      style="--side-width:150px"
    >
      <ion-header>
        <ion-toolbar>
          <ion-title>📦</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-content>
        <a sveltekit:prefetch href=".">
          <ion-item>
            <ion-icon name="home" slot="start" />
            <ion-label>Home</ion-label>
          </ion-item>
        </a>
        <a sveltekit:prefetch href="about">
          <ion-item>
            <ion-icon name="cube" slot="start" />
            <ion-label>About</ion-label>
          </ion-item>
        </a>
        <a sveltekit:prefetch href="user">
          <ion-item>
            <ion-icon name="person" slot="start" />
            <ion-label>User</ion-label>
          </ion-item>
        </a>
      </ion-content>
    </ion-menu>
    <div class="ion-page" id="main">
      <ion-header>
        <ion-toolbar>
          <ion-title>
            <nav>
              {#each routes as route}
                <a sveltekit:prefetch href={route.path}>
                  <ion-icon slot="start" name={route.icon} />
                </a>
              {/each}
            </nav>
          </ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-content>
        <slot />
      </ion-content>
    </div>
  </ion-split-pane>
</body>

<style>
  /* your styles go here */
  a {
    text-decoration: none;
  }
</style>
