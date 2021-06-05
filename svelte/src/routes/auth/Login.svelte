<script>
    import { createEventDispatcher } from "svelte";

    export let username = "";
    export let password = "";
    const dispatch = createEventDispatcher();

    function sayHello() {
        alert('Hello')
        dispatch("success", {
            text: "Success!",
        });
    }
</script>

<form on:submit={() => sayHello()} method="get" >
    <fieldset>
        <legend>Login</legend>
        <input
            type="text"
            bind:value={username}
            name="username"
            placeholder="username"
        />
        <input
            type="password"
            bind:value={password}
            name="password"
            placeholder="password"
        />
        <button type="submit">Login</button>
    </fieldset>
</form>
