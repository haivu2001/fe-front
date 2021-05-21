<script>
    import {fly} from 'svelte/transition'
    import {currentView} from "./currentView";

    let current = 0
</script>

<div class="intro-slides" on:click={() => current+= current == 2 ? 0 : 1}>
    {#if current == 0}
        <div out:fly={{x: -2000,duration: 100}}>
            <h2>
                CHÀO MỪNG BẠN ĐẾN
            </h2>
            <img src="images/biglogo.png"/>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="160" height="160">
                <path fill="none" d="M0 0h24v24H0z"/>
                <path d="M4 6.414L.757 3.172l1.415-1.415L5.414 5h15.242a1 1 0 0 1 .958 1.287l-2.4 8a1 1 0 0 1-.958.713H6v2h11v2H5a1 1 0 0 1-1-1V6.414zM6 7v6h11.512l1.8-6H6zm-.5 16a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3zm12 0a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3z"
                      fill="rgba(222,48,33,1)"/>
            </svg>
        </div>
    {:else if current == 1}
        <div in:fly={{x: 1000,duration: 300}} out:fly={{x: -1000,duration: 100}}>
            <h2>TIẾT KIỆM THỜI GIAN KHI LỰA CHỌN CÁC MÓN ĂN</h2>
            <svg xmlns="http://www.w3.org/2000/svg" width="160" height="160" fill="rgba(222,48,33,1)"
                 class="bi bi-hourglass-split" viewBox="0 0 16 16">
                <path d="M2.5 15a.5.5 0 1 1 0-1h1v-1a4.5 4.5 0 0 1 2.557-4.06c.29-.139.443-.377.443-.59v-.7c0-.213-.154-.451-.443-.59A4.5 4.5 0 0 1 3.5 3V2h-1a.5.5 0 0 1 0-1h11a.5.5 0 0 1 0 1h-1v1a4.5 4.5 0 0 1-2.557 4.06c-.29.139-.443.377-.443.59v.7c0 .213.154.451.443.59A4.5 4.5 0 0 1 12.5 13v1h1a.5.5 0 0 1 0 1h-11zm2-13v1c0 .537.12 1.045.337 1.5h6.326c.216-.455.337-.963.337-1.5V2h-7zm3 6.35c0 .701-.478 1.236-1.011 1.492A3.5 3.5 0 0 0 4.5 13s.866-1.299 3-1.48V8.35zm1 0v3.17c2.134.181 3 1.48 3 1.48a3.5 3.5 0 0 0-1.989-3.158C8.978 9.586 8.5 9.052 8.5 8.351z"/>
            </svg>
        </div>
    {:else if current == 2}
        <div in:fly={{x: 1000,duration: 300}} out:fly={{x: -1000,duration: 100}}>
            <h2>TIẾT KIỆM TIỀN KHI MUA CÁC MÓN ĂN</h2>
            <svg xmlns="http://www.w3.org/2000/svg" width="160" height="160" fill="rgba(222,48,33,1)"
                 class="bi bi-currency-exchange" viewBox="0 0 16 16">
                <path d="M0 5a5.002 5.002 0 0 0 4.027 4.905 6.46 6.46 0 0 1 .544-2.073C3.695 7.536 3.132 6.864 3 5.91h-.5v-.426h.466V5.05c0-.046 0-.093.004-.135H2.5v-.427h.511C3.236 3.24 4.213 2.5 5.681 2.5c.316 0 .59.031.819.085v.733a3.46 3.46 0 0 0-.815-.082c-.919 0-1.538.466-1.734 1.252h1.917v.427h-1.98c-.003.046-.003.097-.003.147v.422h1.983v.427H3.93c.118.602.468 1.03 1.005 1.229a6.5 6.5 0 0 1 4.97-3.113A5.002 5.002 0 0 0 0 5zm16 5.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0zm-7.75 1.322c.069.835.746 1.485 1.964 1.562V14h.54v-.62c1.259-.086 1.996-.74 1.996-1.69 0-.865-.563-1.31-1.57-1.54l-.426-.1V8.374c.54.06.884.347.966.745h.948c-.07-.804-.779-1.433-1.914-1.502V7h-.54v.629c-1.076.103-1.808.732-1.808 1.622 0 .787.544 1.288 1.45 1.493l.358.085v1.78c-.554-.08-.92-.376-1.003-.787H8.25zm1.96-1.895c-.532-.12-.82-.364-.82-.732 0-.41.311-.719.824-.809v1.54h-.005zm.622 1.044c.645.145.943.38.943.796 0 .474-.37.8-1.02.86v-1.674l.077.018z"/>
            </svg>
            <br/>
            <br/>
            <br/>
            <button class="full-width" on:click={() => $currentView = "location"}>
                Bắt đầu
            </button>
        </div>
    {/if}
    <div class="dots">
        <span style="background: {current == 0 ? 'white' : 'hsl(0, 0%, 80%)'}"></span>
        <span style="background: {current == 1 ? 'white' : 'hsl(0, 0%, 80%)'}"></span>
        <span style="background: {current == 2 ? 'white' : 'hsl(0, 0%, 80%)'}"></span>
    </div>
</div>

<style>
    .intro-slides {
        height: 100%;
        background: rgb(206, 240, 241);
        padding: 1.5rem;
        display: flex;
        flex-direction: column;
    }

    .intro-slides > div {
        flex-grow: 1;
    }

    .intro-slides > .dots {
        flex: 0 48px;
    }

    .dots {
        display: flex;
        justify-content: center;
        align-items: end;
        column-gap: 1rem;
    }

    .dots > span {
        border: 1px solid rgba(0, 0, 0, 0);
        background: hsl(0, 0%, 80%);
        width: 1.5rem;
        height: 1.5rem;
        border-radius: 100%;
    }
</style>