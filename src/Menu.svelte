<script>
    import {currentMenu} from "./currentMenu";
    import {currentCombo} from "./currentCombo";

    let menu = {
        "morning": [
            {name: "combo 1", picture: "https://via.placeholder.com/64"},
            {name: "combo 2", picture: "https://via.placeholder.com/64"},
            {name: "combo 3", picture: "https://via.placeholder.com/64"},
        ],
        "afternoon":
            [
                {name: "combo 1", picture: "https://via.placeholder.com/64"},
                {name: "combo 2", picture: "https://via.placeholder.com/64"},
                {name: "combo 3", picture: "https://via.placeholder.com/64"},
            ],
        "evening": [
            {name: "combo 1", picture: "https://via.placeholder.com/64"},
            {name: "combo 2", picture: "https://via.placeholder.com/64"},
            {name: "combo 3", picture: "https://via.placeholder.com/64"},
        ]
    }
</script>
{#if $currentMenu === ""}
    <section>
        <h3>Thực đơn sáng</h3>
        <div>
            <div>
                <img src="https://via.placeholder.com/150"/>
                99KCAL
            </div>
            <div>
                <img src="https://via.placeholder.com/150"/>
                99KCAL
            </div>
            <div>
                <img src="https://via.placeholder.com/150"/>
                99KCAL
            </div>
            <div>
                <img src="https://via.placeholder.com/150"/>
                99KCAL
            </div>
            <div>
                <img src="https://via.placeholder.com/150"/>
                99KCAL
            </div>
        </div>
    </section>
    <section>
        <h3>Thực đơn trưa</h3>
        <div>
            <div>
                <img src="https://via.placeholder.com/150"/>
                99KCAL
            </div>
            <div>
                <img src="https://via.placeholder.com/150"/>
                99KCAL
            </div>
            <div>
                <img src="https://via.placeholder.com/150"/>
                99KCAL
            </div>
        </div>
    </section>
    <section>
        <h3>Thực đơn chiều</h3>
        <div>
            <div>
                <img src="https://via.placeholder.com/150"/>
                99KCAL
            </div>
            <div>
                <img src="https://via.placeholder.com/150"/>
                99KCAL
            </div>
            <div>
                <img src="https://via.placeholder.com/150"/>
                99KCAL
            </div>
        </div>
    </section>
{:else}
    <section>
        <h3>Thực đơn {$currentMenu}</h3>
        {#each menu[$currentMenu] as item}
            <div style="margin-bottom: 0.5rem; border: {$currentCombo === item.name ? '1px solid black' : 'none'}"
                 on:click={() => $currentCombo = item.name}>
                <div>
                    <img src={item.picture}/>
                </div>
                <div><h4>{item.name}</h4></div>
            </div>
        {/each}


    </section>
    <section>
        <div>
            <input placeholder="Nhập địa chỉ Circle K gần bạn nhất"/>
        </div>
    </section>
{/if}
<style>
    section > div {
        display: flex;
        column-gap: 0.5rem;
        overflow-x: auto;
    }

    section > div > div {
        flex-grow: 1;
        text-align: center;
    }

    h3 {
        color: blue;
    }

    img {
        width: 4rem;
    }
</style>