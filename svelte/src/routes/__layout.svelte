<body>
  <ion-split-pane content-id="main" when="md">
    <ion-menu content-id="main" side="start" type="overlay">
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
        <a sveltekit:prefetch href="profile">
          <ion-item>
            <ion-icon name="person" slot="start" />
            <ion-label>Profile</ion-label>
          </ion-item>
        </a>
      </ion-content>
    </ion-menu>
    <div class="ion-page" id="main">
      <ion-header>
        <ion-toolbar>
          <ion-title>
            <a href="/">home</a>|
            <a href="/about">about</a>|
            <a href="/profile">profile</a>
          </ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-content>
        <slot />
      </ion-content>
    </div>
  </ion-split-pane>
</body>
