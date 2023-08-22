<script>
    import { spring} from 'svelte/motion';
	export let myValue = 'default value'
    export let myString = 'default string'
    let myHtml = `<b>Hello custom html</b>`;
    let count = 0
    let inputText = 'Type Below 😁'
    let handleTextChange = (e) => {
        console.log('called me')
        inputText = e.target.value
    }
    let myArrObj = [
        {
            id: 1,
            name: 'Tripto'
        },
        {
            id: 2,
            name: 'Alina'
        },
        {
            id: 3,
            name: 'Juni'
        }
    ]
    const displayed_value = spring();
    $: displayed_value.set(myValue)
    
</script>

<div class="flex-column my-container">
	My Own Svelte Component
   <p>Custom Value: {myValue}</p> 
   <p>Custom String: {myString}</p> 
   <p>Pi: {Math.PI}</p> 
   <p>Random Num: {Math.floor(Math.random()*10)}</p> 
   <ul>{#each myArrObj  as item}
    <li>{item.name}</li>
   {/each}</ul> 
   <p>Count: {count}</p>
   <button type="button" on:click={() => count++}>+</button>
   <button type="button" on:click={() => count--}>-</button>
   <p>{inputText}</p>
   <input placeholder="type here" on:change={handleTextChange} class="px-2 py-2">
   <div class="mt-3">{@html myHtml}</div>
</div>

<style>
    .my-container{
        border: 1px solid greenyellow;
        padding: 10px;
    }
	.flex-column{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
</style>
