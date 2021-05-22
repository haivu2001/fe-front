<script>
    let kcal = 90
</script>

<section>
    <h2>TỔNG KCAL</h2>
</section>
<section>
    <svg viewBox="0 0 100 100">
        <circle r="45" cx="50" cy="50" fill="none" stroke="lightgray" stroke-width="10"/>
        <circle r="45" cx="50" cy="50" fill="none" stroke="orange" stroke-dasharray="283"
                stroke-dashoffset="{kcal/100*283}"
                stroke-width="10"/>
        <text x="50" y="50" font-size="12" text-anchor="middle">Kcal/ngày</text>
        <text x="50" y="60" font-size="10" text-anchor="middle">{kcal}</text>
    </svg>
</section>
<section>
    <div>
        <h3>Bữa sáng</h3>
    </div>
</section>
<section>
    <div>
        <h3>Bữa trưa</h3>
    </div>
</section>
<section>
    <div>
        <h3>Bữa chiều</h3>
    </div>
</section>
<section>&nbsp;</section>

<style>
    section > div {
        padding: 0.2rem;
        margin-top: 1.0rem;
        background: #efefef;
        border-radius: 10px;
    }
</style>