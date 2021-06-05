<body>
  <ion-split-pane content-id="main" when="md">
    <ion-menu content-id="main" side="start" type="overlay">
      <ion-header>
        <ion-toolbar>
          <ion-title>📦</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-content>
        <a href=".">home</a>
        <a href="about">about</a>
        <a href="profile">profile</a>
      </ion-content>
    </ion-menu>
    <ion-content id="main">
      <ion-header>
        <ion-toolbar>
          <ion-title>
            <a href="/">home</a>|
            <a href="/about">about</a>|
            <a href="/auth">profile</a>
          </ion-title>
        </ion-toolbar>
      </ion-header>
      <slot />
    </ion-content>
  </ion-split-pane>
</body>
