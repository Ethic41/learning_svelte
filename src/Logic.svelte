<script>
    let user = {loggedIn: false}

    function toggle(){
        user.loggedIn = !user.loggedIn
    }

    let x = 7;

    let cats = [
        {id: '753afd234', name: 'Fluffy', age: 3},
        {id: '753afd235', name: 'Spot', age: 7},
        {id: '753afd236', name: 'Whiskers', age: 1},
        {id: '753afd237', name: 'Buster', age: 4},
        {id: '753afd238', name: 'Bella', age: 2},
    ];
</script>

<main>
    {#if user.loggedIn}
        <button on:click={toggle}>Log out</button>
        {#if x > 10}
            <p>{x} is greater than 10</p>
        {:else if x < 5}
            <p>{x} is less than 5</p>
        {:else}
            <p>{x} is between 5 and 10</p>
        {/if}
    {:else}
        <button on:click={toggle}>Log in</button>
    {/if}

    {#each cats as cat}
        <p>{cat.name} is {cat.age} years old</p>
    {/each}
</main>

<style>
    main {
        text-align: center;
        padding: 1em;
        max-width: 240px;
        margin: 0 auto;
    }
</style>