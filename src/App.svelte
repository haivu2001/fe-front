<script>
    import Header from "./Header.svelte";
    import Footer from "./Footer.svelte";
    import {currentView} from "./currentView";
    import IntroSlides from "./IntroSlides.svelte";
    import Location from "./Location.svelte";
    import Menu from "./Menu.svelte";
    import Login from "./Login.svelte";

</script>

<svelte:head>
    <title>FitEater PWA</title>
</svelte:head>

<div class="view">
    {#if $currentView !== "intro"}
        <main>
            {#if $currentView === "location"}
                <Location/>
            {:else if $currentView === "menu"}
                <Menu/>
            {:else if $currentView === "login"}
                <Login/>
            {/if}
        </main>
        {#if $currentView !== "location" && $currentView !== "login"}
            <header>
                <Header/>
            </header>
            <footer>
                <Footer/>
            </footer>
        {/if}
    {:else }
        <IntroSlides/>
    {/if}

</div>

<style>
    @media (min-width: 640px) {
        .view {
            max-width: 480px;
        }
    }

    .view {
        background: white;
        width: 100%;
        height: 100%;
        margin: 0 auto;
        display: flex;
        flex-direction: column;
        justify-content: stretch;
        position: relative;
    }

    .view > * {
        flex-grow: 1;
    }

    .view > header {
        order: -1;
        flex: 0 20px;
        display: flex;
    }

    .view > footer {
        order: 1;
        flex: 0 16px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        border-top: 2px solid black;
    }

    .view > main {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        padding-left: 1.5rem;
        padding-right: 1.5rem;
    }

    .view > main > * {
        flex-grow: 1;
    }


</style>