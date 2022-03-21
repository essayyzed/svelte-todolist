<script>
    // import {createEventDispatcher} from "svelte";
    import { each } from 'svelte/internal';

    import Todo from './Todo.svelte';
    export let todos;

    // const dispatch = createEventDispatcher();
    // function forward(event) {
    //     // console.log("In todos: ", event.detail);
    //     dispatch("completed", event.detail)
    // }

</script>

<!-- List of actual todos -->
<div class="app-body">
    <ul>
        {#each todos as todo}
            <Todo
                itemId={todo.id}
                itemText={todo.text}
                completed={todo.completed}
                on:completed
            />
        {/each}
    </ul>
</div>

<style>
    .app-body {
        flex-grow: 1;
        max-height: 600px;
        overflow-x: hidden;
    }
    ul {
        list-style-type: none;
        -webkit-padding-start: 0;
        padding-left: 0px;
    }
</style>
