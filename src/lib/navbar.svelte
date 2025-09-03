<script>
</script>

<nav>
    <ul>
        <li class="fc"><a href="/">ffinder</a></li>
    </ul>
    <!-- <ul>
        <li style="cursor: default;">
            <a href="/donate"> <button class="fc orange">Donate!</button></a>
        </li>
    </ul> -->
    <ul></ul>
    <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/scan">Scan</a></li>
        <li><a href="/connect">Connect</a></li>
        <!-- svelte-ignore a11y_missing_attribute -->
        <li class="fc">
            <a class="fc" href="/account"
                >Account&nbsp;<img class="fc" src="src\image.png" /></a
            >
        </li>
    </ul>
</nav>

<style>
    /* * {
        border: 1px solid red;
    }  */

    nav {
        padding: 0rem 1rem;
        background-color: #ababab;
        height: 75px;
    }

    * {
        color: black;
    }

    a:hover {
        color: white;
        text-decoration: none;
    }

    img {
        width: 30px;
        height: 30px;
        border-radius: 100px;
        object-fit: cover;
    }

    /* button {
        height: 28px;
    }

    button:hover {
        color: white;
    } */
</style>
