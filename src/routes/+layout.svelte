<script>
    import Navbar from "$lib/navbar.svelte";
    import "$lib/global.css";
</script>

<Navbar />
<div class='fc sf-nav'>
    <slot />
</div>

<style>
    div {
        margin: 0px 50px 0px 50px;

    }
</style>
