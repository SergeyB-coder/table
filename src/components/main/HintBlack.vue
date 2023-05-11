<template>
    <div class="hint">
        <div class="hint__text">
            Статистика, которая “доходит” от источников, по уже отключенным доставкам
        </div>

        <svg class="hint__arrow_down" width="20" height="12" viewBox="0 0 20 12" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M9.26545 11.2048C9.66137 11.6334 10.3386 11.6334 10.7346 11.2048L18.8417 2.42855C19.4334 1.78807 18.9791 0.75 18.1072 0.75H1.89283C1.0209 0.75 0.566624 1.78807 1.15827 2.42855L9.26545 11.2048Z" fill="black"/>
        </svg>
    </div>
</template>


<style scoped>
.hint__arrow_down {
    position: absolute;
    bottom: -10px;
    left: calc(50% - 10px)
}
.hint__text {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 20px;
    /* or 143% */

    text-align: center;
    letter-spacing: 0.005em;

    color: #FFFFFF;
}

.hint {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 8px 10px;
    gap: 4px;
    isolation: isolate;

    position: absolute;
    width: 15vw;
    height: 96px;
    left: -7vw;
    bottom: 30px;

    /* Gray/900 */

    background: #000000;
    border-radius: 6px;
}
</style>