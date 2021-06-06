<script>
  import Register from "./Register.svelte";

  import Login from "./Login.svelte";
  import { user } from "$lib/stores/stores";
  import Profile from "./Profile.svelte";

  let username, password;
  let email = `${username}@email.pea.co.th`;
  function handleSubmit(ev) {
    alert(email);
  }
</script>

{#if user}
  <Profile />
{:else}
  <Login on:success={handleSubmit} />

  <Register on:success={handleSubmit} />
{/if}

<style>
</style>
