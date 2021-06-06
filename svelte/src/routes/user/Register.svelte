<script>
  import { createEventDispatcher } from "svelte";

  export let username = "";
  export let password = "";
  export let email = "";
  const dispatch = createEventDispatcher();
  function regis() {
    alert("Hello");
    dispatch("success", {
      text: "Success!",
    });
  }
</script>

<ion-card>
  <ion-card-header>
    <ion-card-title>ลงทะเบียน</ion-card-title>
  </ion-card-header>
  <form on:submit|preventDefault={regis} autocomplete="on">
    <ion-card-content>
      <ion-item>
        <ion-label position="floating">E-Mail</ion-label>
        <ion-input type="email" name="email" id="email" placeholder="E-mail" />
      </ion-item>
      <ion-item>
        <ion-label position="floating">Username</ion-label>
        <ion-input
          type="text"
          name="username"
          id="username"
          placeholder="Username"
        />
      </ion-item>
      <ion-item>
        <ion-label position="floating"
          >Password <ion-text color="danger">*</ion-text></ion-label
        >
        <ion-input
          required
          type="password"
          name="password"
          placeholder="password"
          auto-complete="cc-password"
          id="password"
        />
      </ion-item>
      <button type="submit" />
      <ion-button type="submit" fill="solid" shape="round">
        Register
      </ion-button>
    </ion-card-content>
  </form>
</ion-card>

<style>
</style>
