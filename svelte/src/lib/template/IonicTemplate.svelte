<script>
  export let routes = [
    { name: "Home", icon: "home", path: "/" },
    { name: "Information", icon: "information", path: "/about" },
    { name: "User", icon: "person", path: "/user" },
    { name: "Blogs", icon: "cube", path: "/blogs" },
    { name: "Calendar", icon: "calendar", path: "celendar" },
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
        <ion-toolbar color="secondary">
          <ion-buttons slot="start">
            <ion-menu-button menu="main" />
          </ion-buttons>
          <ion-buttons slot="secondary">
            <ion-button>
              <ion-icon slot="icon-only" name="person-circle" />
            </ion-button>
            <ion-button>
              <ion-icon slot="icon-only" name="search" />
            </ion-button>
          </ion-buttons>
          <ion-buttons slot="primary">
            <ion-button color="primary">
              <ion-icon
                slot="icon-only"
                ios="ellipsis-horizontal"
                md="ellipsis-vertical"
              />
            </ion-button>
          </ion-buttons>
          <ion-title>PBOX</ion-title>
        </ion-toolbar>
      </ion-header>
      <nav>
        {#each routes as route}
          <a sveltekit:prefetch href={route.path}>
            <ion-button>
              <ion-icon slot="icon-only" name={route.icon} />
            </ion-button>
          </a>
        {/each}
      </nav>
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
