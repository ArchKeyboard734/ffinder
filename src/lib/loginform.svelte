<form action="authenticate.php" method="post">
    <input
        minlength="3"
        maxlength="32"
        type="text"
        name="username"
        placeholder="Username"
        id="username"
        required
    />
    <input
        minlength="3"
        maxlength="32"
        type="password"
        name="password"
        placeholder="Password"
        id="password"
        required
    />

    <button class="btn" type="submit">Login</button>

    <p>Don't have an account? <a href="register.php">Register</a></p>
</form>
