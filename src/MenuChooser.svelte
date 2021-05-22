<script>
    import {currentMenu} from "./currentMenu";
    import {createEventDispatcher} from 'svelte'

    const dispatch = createEventDispatcher()

    function selectMenu(menu) {
        $currentMenu = menu
        dispatch('selected')
    }
</script>

<div class="container">
    <button class="full-width selectable" on:click={() => selectMenu("morning")}> Sáng</button>
    <button class="full-width selectable" on:click={() => selectMenu("afternoon")}>Trưa</button>
    <button class="full-width selectable" on:click={() => selectMenu("evening")}>Chiều</button>
</div>

<style>
    .container {
        position: fixed;
        top: 20%;
        width: 70%;
        left: 15%;
        padding: 1.5rem;
        border: 2px solid black;
        box-sizing: border-box;
        border-radius: 20px;
        background: rgba(200, 200, 200, 0.6);
    }
</style>