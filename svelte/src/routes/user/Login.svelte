<script>
  import { createEventDispatcher } from "svelte";

  export let username = "";
  export let password = "";
  const dispatch = createEventDispatcher();

  function login() {
    alert("Hello");
    dispatch("success", {
      text: "Success!",
    });
  }
</script>


<form action="summit" on:submit|preventDefault={login}>
  <ion-card>
    <ion-card-header>
      <ion-card-title>ลงชื่อเข้าใช้</ion-card-title>
    </ion-card-header>
    <ion-card-content>
      <ion-item>
        <ion-label position="floating">Username</ion-label>
        <ion-input type="text" name="username" placeholder="username" />
      </ion-item>
      <ion-item>
        <ion-label position="floating"
          >Password <ion-text color="danger">*</ion-text></ion-label
        >
        <ion-input required type="password" placeholder="password" />
      </ion-item>
      <ion-button type="submit" on:enter fill="solid" shape="round">
          Login
      </ion-button>
    </ion-card-content>
  </ion-card>
</form>
