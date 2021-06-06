<script>
  import { page } from "$app/stores";
</script>

<body>
  <ion-app>
    <ion-split-pane when="sm" content-id="main-content">
      <ion-menu
        content-id="main-content"
        side="start"
        style="--side-width:150px;"
      >
        <ion-header>
          <ion-toolbar color="primary">
            <ion-title>Menu</ion-title>
          </ion-toolbar>
        </ion-header>

        <ion-content>
          <ion-list>
            <ion-menu-toggle auto-hide="false">
              <a sveltekit:prefetch href="/">
                <ion-item button>
                  <ion-icon slot="start" name="home" />
                  <ion-label> Home </ion-label>
                </ion-item>
              </a>
            </ion-menu-toggle>
            <ion-menu-toggle auto-hide="false">
              <a sveltekit:prefetch href="blogs">
                <ion-item button>
                  <ion-icon slot="start" name="library" />
                  <ion-label> Blogs </ion-label>
                </ion-item>
              </a>
            </ion-menu-toggle>
          </ion-list>
        </ion-content>
      </ion-menu>

      <div class="ion-page" id="main-content">
        <ion-header>
          <ion-toolbar color="light">
            <ion-buttons slot="start">
              <ion-menu-toggle>
                <ion-button>
                  <ion-icon slot="icon-only" name="menu" />
                </ion-button>
              </ion-menu-toggle>
              <ion-button>
                <a sveltekit:prefetch href=".">
                  <ion-icon slot="icon-only" name="home" />
                </a>
              </ion-button>
            </ion-buttons>
            <ion-buttons slot="secondary">
              <ion-button>
                <a href="user">
                  <ion-icon slot="icon-only" name="person-circle" />
                </a>
              </ion-button>
              <ion-button>
                <a href="search">
                  <ion-icon slot="icon-only" name="search" />
                </a>
              </ion-button>
            </ion-buttons>
            <ion-buttons slot="primary">
              <ion-button color="danger">
                <ion-icon
                  slot="icon-only"
                  ios="ellipsis-horizontal"
                  md="ellipsis-vertical"
                />
              </ion-button>
            </ion-buttons>
            <ion-title>Dark Toolbar</ion-title>
          </ion-toolbar>
        </ion-header>
        <ion-content class="ion-padding">
          <slot><!-- optional fallback --></slot>
        </ion-content>
      </div>
    </ion-split-pane>
  </ion-app>
</body>

<!-- markup (zero or more items) goes here -->
<style global>
  @tailwind utilities;
  /* your styles go here */
</style>
