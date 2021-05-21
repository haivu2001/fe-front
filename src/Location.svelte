<script>
    let selected = ""
</script>

<section>
    <h2>
        VỊ TRÍ CỦA BẠN
    </h2>

    <button class="full-width selectable" class:selected={selected === "cs1"} on:click={() => selected = "cs1"}>
        ĐẠI HỌC BÁCH KHOA CS1
    </button>
    <button class="full-width selectable" class:selected={selected === "cs2"} on:click={() => selected = "cs2"}>
        ĐẠI HỌC BÁCH KHOA CS2
    </button>
    <button class="full-width selectable" class:selected={selected === "ktxa"} on:click={() => selected = "ktxa"}>
        KTX ĐẠI HỌC QUỐC GIA
    </button>
</section>
<section>
    {#if selected}
        <button class="full-width">TIẾP TỤC</button>
    {/if}
</section>