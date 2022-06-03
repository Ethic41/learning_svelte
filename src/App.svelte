<script>
    import Nested from './Nested.svelte';
    import Reactivity from './Reactivity.svelte';
    import Props from './Props.svelte';
    import Logic from './Logic.svelte';
	export let name;
    
    let new_name = "awesome svelte";
    let user = "John Doe";
    let src = 'https://picsum.photos/200/300';
    let string = `This is a <strong>cool</strong> paragraph.`;

    const pkg = {
        name: 'svelte',
        version: 3.0,
        speed: 'blazing',
        website: 'https://svelte.dev'
    };
</script>

<main>
	<h1>Hello {name}!</h1>
    <h2>Hi, {new_name}!</h2>
    <h2>Hi, {user.toUpperCase()}!</h2>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>

    <!-- Dynamic attributes -->
    <img src={src} alt="some random {user}">
    <Nested answer={42}/>
    <p>{@html string}</p>
    <Reactivity/>
    <Props {...pkg}/>
    <Logic/>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}

    p {
        color: #ff3e00;
        font-family: 'Courier New', Courier, monospace;
        font-size: 2em;
    }
</style>