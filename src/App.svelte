<script>

</script>

<div class="view">
    <header>header</header>
    <main>hello</main>
    <footer>hello</footer>
</div>

<style>
    @media (min-width: 640px) {
        .view {
            max-width: 640px;
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
        flex: 0 48px;
    }

    .view > footer {
        flex: 0 64px;
    }
</style>