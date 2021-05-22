<script>
    import {currentView} from "./currentView";

    let register = false
</script>

<section>
    <img src="images/biglogo.png"/>
</section>
<section>
    <small>VUI LÒNG ĐĂNG NHẬP ĐỂ CHÚNG TÔI CÓ THỂ PHỤC VỤ BẠN TỐT HƠN</small>
</section>
<section style="margin-top: 64px">
    <div>
        <div style="background: darkcyan; padding: 1.4rem; position: absolute;height: 64px;top:-64px;box-sizing: border-box;color: white;border-top-left-radius: 10px;border-top-right-radius: 10px;font-weight: bold;    font-family: Verdana, sans-serif;">
            {#if !register}
                ĐĂNG NHẬP
            {:else}
                ĐĂNG KÍ
            {/if}
        </div>
        <label> EMAIL <input type="email" placeholder="EX: user123@example.com"/></label>
        <label> MẬT KHẨU <input type="password" placeholder="EX: abc123"/></label>
        {#if register}
            <label> HỌ VÀ TÊN <input placeholder="EX: Nguyễn Văn A"/></label>
            <label> GIỚI TÍNH
                <select>
                    <option value="male">Nam</option>
                    <option value="female">Nữ</option>
                </select>
            </label>

        {/if}
        {#if !register}
            <button class="full-width" on:click={() => $currentView = "dashboard"}>ĐĂNG NHẬP</button>
            <div>
                Chưa có tài khoản? <a href="#" on:click={() => register = true}>Đăng kí</a>
            </div>
        {:else }
            <button class="full-width">ĐĂNG KÍ</button>
        {/if}

    </div>
</section>

<style>
    section > div {
        display: flex;
        position: relative;
        flex-direction: column;
        align-items: center;
        column-gap: 0.5rem;
        border: 3px solid darkcyan;
        border-radius: 10px;
        padding: 1.2rem 0.8rem 0.8rem;
        margin-bottom: 1rem;
    }

    label {
        text-align: center;
        font-weight: bolder;
        width: 100%;
        position: relative;
        color: darkcyan;
    }

    input, select {
        display: block;
        width: 100%;
        box-sizing: border-box;
    }

    button {
        display: block;
    }
</style>