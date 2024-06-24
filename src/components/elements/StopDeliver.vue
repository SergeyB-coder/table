<template>
    <modal-error v-show="show_modal_error"/>
    <modal-done v-show="show_modal_done"/>
    <modal-warning v-show="show_modal_warning"/>
    <div class="cntr-row">
        <part-left/>

        <div class="cntr-bg-2">
            <div v-show="show_modal_error" class="pseudo_bg"></div>
            
            <div class="cntr-table">
                <div class="grey-box w-97 h-40 cntr-row a-c cur-pointer">
                    <svg class="ml-16" width="8" height="14" viewBox="0 0 8 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path fill-rule="evenodd" clip-rule="evenodd" d="M7.35404 0.646009C7.4006 0.692455 7.43754 0.74763 7.46275 0.808375C7.48796 0.86912 7.50093 0.934242 7.50093 1.00001C7.50093 1.06578 7.48796 1.1309 7.46275 1.19164C7.43754 1.25239 7.4006 1.30756 7.35404 1.35401L1.70704 7.00001L7.35404 12.646C7.44793 12.7399 7.50067 12.8672 7.50067 13C7.50067 13.1328 7.44793 13.2601 7.35404 13.354C7.26015 13.4479 7.13281 13.5006 7.00004 13.5006C6.86726 13.5006 6.73993 13.4479 6.64604 13.354L0.646039 7.35401C0.599476 7.30756 0.562533 7.25239 0.537326 7.19164C0.51212 7.1309 0.499146 7.06578 0.499146 7.00001C0.499146 6.93424 0.51212 6.86912 0.537326 6.80838C0.562533 6.74763 0.599476 6.69245 0.646039 6.64601L6.64604 0.646009C6.69248 0.599446 6.74766 0.562503 6.80841 0.537296C6.86915 0.51209 6.93427 0.499115 7.00004 0.499115C7.06581 0.499115 7.13093 0.51209 7.19167 0.537296C7.25242 0.562503 7.30759 0.599446 7.35404 0.646009Z" fill="#6B7280"/>
                    </svg>
                    <div class="text-2 ml-11">Назад</div>
                </div>

                <div class="text-1 mt-15">Остановка доставок</div>

                <div class="line mt-10">
                </div>

                <div class="cntr-row j-b stopdeliver__cntr_input">
                    <textarea class="stopdeliver__input" rows="5" cols="60" name="text" placeholder="Список доставок, построчно или через ;"></textarea>
                    <textarea class="stopdeliver__input" rows="5" cols="60" name="text" placeholder="Результаты работы"></textarea>
                </div>
                
                

                <div class="cntr-user-input mt-15">
                    <div class="input-label txt-a-l">Причина остановки / запуска</div>
                    <div class="mt-15">
                        <input class="input-reason text-6 pl-16" />
                    </div>
                </div>

                
                <div class="btn_stop">
                    Стоп
                </div>     

                    
                
            </div>
        </div>
    </div>
</template>

<script>

import PartLeft from './delivers/PartLeftListDelivers.vue'
import ModalError from './delivers/ModalError.vue'
import ModalDone from './delivers/ModalDone.vue'
import ModalWarning from './delivers/ModalWarning.vue'

export default {
    name: 'StopDeliver',
    data() {
        return {
            accounts: [
                {id: 1, src: 'MyTarget', email: 'dsg@mail.ru', date: '12.03.2023', is_actual: 'Неактуален'},
                {id: 2, src: 'MyTarget', email: 'dsg@mail.ru', date: '12.03.2023', is_actual: 'Неактуален'}
            ],
            show_modal_error: false,
            show_modal_done: false,
            show_modal_warning: true,
        }
    },
    components: {
        'part-left': PartLeft,
        'modal-error': ModalError,
        'modal-done': ModalDone,
        'modal-warning': ModalWarning,
    }
}



</script>

<style scoped>
.pseudo_bg {
    top: 0;
    left: 0;
    position: absolute;
    width: 100%;
    height: 100%;
    background: #6B7280;
    opacity: 0.5;
    background-blend-mode: multiply;
    z-index: 10;
}
.btn_stop {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    /* padding: 10px 16px; */
    gap: 8px;

    width: 70px;
    height: 46px;

    background: #FD9393;
    border-radius: 6px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 15px;
    line-height: 18px;
    text-align: center;
    letter-spacing: 0.005em;

    /* White/White */

    color: #FFFFFF;

    margin-top: 88px;
    cursor: pointer;
}
.stopdeliver__cntr_input {
    width: 77vw;
    margin-top: 15px;
}
.j-b {
    justify-content: space-between;
}
.stopdeliver__input {
    outline: none;
    resize: none;
    width: 37vw;
    height: 284px;

    /* White/White */

    background: #FFFFFF;
    /* Gray/200 */

    border: 1px solid #E5E7EB;
    /* Drop Shadow/sm */

    box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.05);
    border-radius: 6px;

    padding: 14px 16px 0px 16px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 15px;
    line-height: 23px;
    letter-spacing: 0.005em;

    color: #1F2937;
}
.stopdeliver__input:nth-child(2) {
    margin-left: 12px;
}
.cur-pointer {
    cursor: pointer;
}
.svg-email {
    position: absolute;
    left: 16px;
    top: calc(50% - 6px);
}
.cntr-relative {
    position: relative;
}
.select-page {
    display: flex;
    flex-direction: row;
    align-items: center;
    /* padding: 14px 16px; */
    /* gap: 10px; */

    width: 123px;
    height: 46px;

    background: #F2F7FF;
}
.cntr-svg-cancel {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    padding: 0px;

    
    width: 15px;
    height: 15px;

    /* Gray/200 */

    background: #E5E7EB;
    border-radius: 999px;
}

.cntr-page-item {
    display: flex;
    flex-direction: row;
    align-items: center;
    /* padding: 6px; */
    gap: 1px;

    width: 121px;
    height: 28px;

    /* Gray/200 */

    border: 1px solid #E5E7EB;
    border-radius: 999px;
}

.cntr-enabled-pages {
    display: flex;
    flex-direction: row;

    justify-content: space-between;
    align-items: center;
    padding: 0px;

    width: 414px;
    height: 46px;

    overflow: hidden;

    background: #FFFFFF;
    /* Gray/200 */

    border: 1px solid #E5E7EB;
    /* Drop Shadow/sm */

    box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.05);
    border-radius: 6px;
}
.start {
    color: #F87171;
}
.cntr-user-input {
    width: 400px;
    height: 78px
}

.input-label {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 15px;
    line-height: 18px;
    letter-spacing: 0.005em;

    color: #475569;
}

.text-6 {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 15px;
    line-height: 18px;
    letter-spacing: 0.005em;

    /* Gray/500 */

    color: #6B7280;
}

.input-user-email {
    display: flex;
    flex-direction: row;
    align-items: center;
    padding: 0px;

    width: 358px;
    height: 46px;

    background: #F2F7FF;
    border: 1px solid #E5E7EB;
    /* Drop Shadow/sm */

    box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.05);
    border-radius: 6px;
}

.input-reason {
    display: flex;
    flex-direction: row;
    align-items: center;
    padding: 0px;

    width: 37vw;
    height: 46px;

    /* White/White */

    background: #FFFFFF;
    border: 1px solid #E5E7EB;
    border-radius: 6px;
    outline: none;
}

.input-reason:focus {
    border: 1px solid #3B82F6;
/* Focus Ring/Blue-500 */

    box-shadow: 0px 0px 0px 4px rgba(59, 130, 246, 0.25);   
}
.txt-a-l {
    text-align: left;
}
.line {
    /* width: 1050px; */
    height: 1px;

    background: #E5E7EB;
}

.pl-42 {
    padding-left: 42px;
}

.pl-16 {
    padding-left: 16px;
}
.mt-10 {
    margin-top: 10px;
}

.mt-15 {
    margin-top: 15px;
}



.ml-5 {
    margin-left: 5px;
}
.ml-8 {
    margin-left: 8px;
}
.ml-10 {
    margin-left: 10px;
}
.ml-11 {
    margin-left: 11px;
}

.ml-16 {
    margin-left: 16px;
}


.a-c {
    align-items: center;
}

.j-c {
    justify-content: center;
}



.h-40 {
    height: 40px
}
.w-78 {
    width: 78px;
}

.w-97 {
    width: 97px;
}
.h-40 {
    height: 40px;
}
.text-1 {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 20px;
    line-height: 24px;
    letter-spacing: 0.005em;

    color: #000000;

    text-align: left;
}

.text-2 {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 12px;
    line-height: 16px;
    /* identical to box height, or 133% */

    letter-spacing: 0.005em;
    text-align: left;
    /* Gray/500 */

    color: #6B7280;
}






.text-white {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 15px;
    line-height: 18px;
    /* identical to box height, or 150% */

    text-align: center;
    letter-spacing: 0.005em;

    /* White/White */

    color: #FFFFFF;
}
.cntr-table {
    position: relative;
    padding-left: 26px;
    padding-top: 21px;
    padding-right: 27px;
}

.cntr-bg-2 {
    background: #FFFFFF;
    position: relative;
}

.cntr-row {
    display: flex;
}

.grey-box {
    border: 1px solid #E5E7EB;
    /* Drop Shadow/sm */

    box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.05);
    border-radius: 6px;
}

.blue-box {
    width: 114px;
    height: 40px;

    /* Blue/500 */

    background: #3B82F6;
    border-radius: 6px;
}
</style>