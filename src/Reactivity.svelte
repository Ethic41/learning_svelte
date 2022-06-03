<script>
    import Nested from './Nested.svelte';
    let count = 0;
    $: double = count * 2;
    $: {
        console.log(`the count is ${count}`);
        if (count >= 10) {
            alert('count is dangerously high');
            count -= 5;
        }
    }

    function incrementCount(){
        count += 1;
    }

    let numbers = [1, 2, 3, 4, 5];
    function addNumber(){
        numbers = [...numbers, numbers.length + 1];
    }

    $: sum = numbers.reduce((acc, curr) => acc + curr, 0);
</script>

<button on:click={incrementCount}>
    Clicked {count} {count === 1 ? 'time' : 'times'}
</button>
<p>
    {count} doubled is {double}
</p>

<p>{numbers.join(' + ')} = {sum}</p>

<button on:click={addNumber}>
    Add a number
</button>
<Nested answer={count}/>
<Nested/>

<style>
    button {
        background-color: #ff3e00;
        color: #ffffff;
        padding: 0.5em;
        font-size: 1em;
        font-weight: 100;
        cursor: pointer;
        border-radius: 5px;
    }

    p {
        font-size: 1.5em;
        font-weight: 100;
        color: #ff3e00;
    }
</style>