<template>
    <div class="box">
        <h3 class="box-title">
            Advice #{{ quote.id }}
        </h3>
        <p class="quote">
            "{{ quote.content }}"
        </p>
        <img src="../assets/pattern-divider-desktop.svg" class="divider-img" alt="">
        <button class="btn" @click="getAdvice">
            <img src="../assets/icon-dice.svg" alt="Dice Icon">
        </button>
    </div>
</template>

<script>

export default {
    props: ['quote', 'getAdvice']
}
</script>

<style scoped>
/* Advice Box */
.box {
    position: relative;
    width: 550px;
    min-height: 300px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 50px;
    padding-bottom: 30px;
    background: var(--clr-dk-grayish-blue);
    text-align: center;
    border-radius: 20px;
    transition: all 0.2s;
}
.box-title {
    padding-bottom: 20px;
    text-transform: uppercase;
    font-size: 15px;
    letter-spacing: 3.5px;
    color: var(--clr-neon-green);
    font-weight: 400;
}
.quote {
    font-size: 28px;
    font-weight: 700;
}
.divider-img {
    width: 100%;
    padding: 40px 0;
    pointer-events: none;
    user-select: none;
}
/* Button Styles */
.btn {
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translate(-50%, 50%);
    display: flex;
    justify-content: center;
    align-items: center;
    width: 70px;
    height: 70px;
    border-radius: 50%;
    border: none;
    outline: none;
    background: var(--clr-neon-green);
    cursor: pointer;
    transition: all 0.3s;
}
.btn img {
    width: 25px;
}
.btn:hover {
    box-shadow: 0 0 25px 3px var(--clr-neon-green);
}
/* RWD */
@media only screen and (max-width: 550px) {
    .box {
        margin: 0 20px;
        padding: 40px 30px;
    }
    .quote {
        font-size: 24px;
    }
}
</style>
