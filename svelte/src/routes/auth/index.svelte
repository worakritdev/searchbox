<script>
    import Login from "./Login.svelte";

    let username, password;

    function handleSubmit(ev) {
        alert(ev);
    }
</script>

<Login on:success={handleSubmit} />

<style>
</style>
