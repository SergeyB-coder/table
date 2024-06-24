<template>
    <div class="cntr-row">
        <part-left/>

        <div class="cntr-bg-2">
            <div class="cntr-table">

                <div class="grey-box w-97 h-40 cntr-row a-c cur-pointer">
                    <svg class="ml-16" width="8" height="14" viewBox="0 0 8 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path fill-rule="evenodd" clip-rule="evenodd" d="M7.35404 0.646009C7.4006 0.692455 7.43754 0.74763 7.46275 0.808375C7.48796 0.86912 7.50093 0.934242 7.50093 1.00001C7.50093 1.06578 7.48796 1.1309 7.46275 1.19164C7.43754 1.25239 7.4006 1.30756 7.35404 1.35401L1.70704 7.00001L7.35404 12.646C7.44793 12.7399 7.50067 12.8672 7.50067 13C7.50067 13.1328 7.44793 13.2601 7.35404 13.354C7.26015 13.4479 7.13281 13.5006 7.00004 13.5006C6.86726 13.5006 6.73993 13.4479 6.64604 13.354L0.646039 7.35401C0.599476 7.30756 0.562533 7.25239 0.537326 7.19164C0.51212 7.1309 0.499146 7.06578 0.499146 7.00001C0.499146 6.93424 0.51212 6.86912 0.537326 6.80838C0.562533 6.74763 0.599476 6.69245 0.646039 6.64601L6.64604 0.646009C6.69248 0.599446 6.74766 0.562503 6.80841 0.537296C6.86915 0.51209 6.93427 0.499115 7.00004 0.499115C7.06581 0.499115 7.13093 0.51209 7.19167 0.537296C7.25242 0.562503 7.30759 0.599446 7.35404 0.646009Z" fill="#6B7280"/>
                    </svg>
                    <div class="text-2 ml-11">Назад</div>
                </div>

                <div class="text-1 mt-15">Создание пользователя</div>

                <div class="line mt-10">
                </div>

                <!-- USER INPUT -->
                <div class="cntr-user-input mt-15">
                    <div class="input-label txt-a-l">Имя <span class="start">*</span></div>
                    <div class="mt-15">
                        <input class="input-user-name text-6 pl-16" />
                    </div>
                </div>

                <div class="cntr-user-input mt-15">
                    <div class="input-label txt-a-l">Email <span class="start">*</span></div>
                    <div class="cntr-relative mt-15">

                        
                        <svg class="svg-email" width="16" height="12" viewBox="0 0 16 12" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M0 2C0 1.46957 0.210714 0.960859 0.585786 0.585786C0.960859 0.210714 1.46957 0 2 0H14C14.5304 0 15.0391 0.210714 15.4142 0.585786C15.7893 0.960859 16 1.46957 16 2V10C16 10.5304 15.7893 11.0391 15.4142 11.4142C15.0391 11.7893 14.5304 12 14 12H2C1.46957 12 0.960859 11.7893 0.585786 11.4142C0.210714 11.0391 0 10.5304 0 10V2ZM2 1C1.73478 1 1.48043 1.10536 1.29289 1.29289C1.10536 1.48043 1 1.73478 1 2V2.217L8 6.417L15 2.217V2C15 1.73478 14.8946 1.48043 14.7071 1.29289C14.5196 1.10536 14.2652 1 14 1H2ZM15 3.383L10.292 6.208L15 9.105V3.383ZM14.966 10.259L9.326 6.788L8 7.583L6.674 6.788L1.034 10.258C1.09083 10.4708 1.21632 10.6589 1.39099 10.7931C1.56566 10.9272 1.77975 11 2 11H14C14.2201 11 14.4341 10.9274 14.6088 10.7934C14.7834 10.6595 14.909 10.4716 14.966 10.259V10.259ZM1 9.105L5.708 6.208L1 3.383V9.105Z" fill="#6B7280"/>
                        </svg>

                        <input class="input-user-email pl-42 text-6" placeholder="victoria@ya.ru"/>
                    </div>
                </div>

                <div class="cntr-user-input mt-15">
                    <div class="input-label txt-a-l">Пароль <span class="start">*</span></div>
                    <div class="mt-15">
                        <input class="input-user-name text-6 pl-16" />
                    </div>
                </div>

                <div class="cntr-user-input mt-15">
                    <div class="input-label txt-a-l">Подтверждение пароля <span class="start">*</span></div>
                    <div class="mt-15">
                        <input class="input-user-name text-6 pl-16" />
                    </div>
                </div>

                <!-- ENABLED PAGES -->

                <div class="cntr-user-input mt-15">
                    <div class="input-label txt-a-l">Доступные страницы <span class="start">*</span></div>

                    <div class="cntr-enabled-pages mt-15">

                        <div class="cntr-page-item ml-8">
                            <div class="text-2 ml-10">Пользователи</div>

                            <div class="cntr-svg-cancel ml-5 cur-pointer">
                                <svg width="9" height="8" viewBox="0 0 9 8" fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path fill-rule="evenodd" clip-rule="evenodd" d="M7.42707 1.07296C7.45035 1.09618 7.46882 1.12377 7.48143 1.15414C7.49403 1.18451 7.50052 1.21707 7.50052 1.24996C7.50052 1.28284 7.49403 1.3154 7.48143 1.34578C7.46882 1.37615 7.45035 1.40374 7.42707 1.42696L1.92707 6.92696C1.88013 6.9739 1.81646 7.00027 1.75007 7.00027C1.68368 7.00027 1.62001 6.9739 1.57307 6.92696C1.52613 6.88002 1.49976 6.81635 1.49976 6.74996C1.49976 6.68357 1.52613 6.6199 1.57307 6.57296L7.07307 1.07296C7.09629 1.04968 7.12388 1.03121 7.15425 1.0186C7.18463 1.006 7.21719 0.999512 7.25007 0.999512C7.28296 0.999512 7.31552 1.006 7.34589 1.0186C7.37626 1.03121 7.40385 1.04968 7.42707 1.07296Z" fill="#6B7280"/>
                                    <path fill-rule="evenodd" clip-rule="evenodd" d="M1.57296 1.07296C1.54968 1.09618 1.53121 1.12377 1.5186 1.15414C1.506 1.18451 1.49951 1.21707 1.49951 1.24996C1.49951 1.28284 1.506 1.3154 1.5186 1.34578C1.53121 1.37615 1.54968 1.40374 1.57296 1.42696L7.07296 6.92696C7.1199 6.9739 7.18357 7.00027 7.24996 7.00027C7.31635 7.00027 7.38002 6.9739 7.42696 6.92696C7.4739 6.88002 7.50027 6.81635 7.50027 6.74996C7.50027 6.68357 7.4739 6.6199 7.42696 6.57296L1.92696 1.07296C1.90374 1.04968 1.87615 1.03121 1.84578 1.0186C1.8154 1.006 1.78284 0.999512 1.74996 0.999512C1.71707 0.999512 1.68451 1.006 1.65414 1.0186C1.62377 1.03121 1.59618 1.04968 1.57296 1.07296Z" fill="#6B7280"/>
                                </svg>
                            </div>
                        </div>

                        <div class="cntr-page-item ml-5">
                            <div class="text-2 ml-10">Целостность</div>

                            <div class="cntr-svg-cancel ml-5 cur-pointer">
                                <svg width="9" height="8" viewBox="0 0 9 8" fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path fill-rule="evenodd" clip-rule="evenodd" d="M7.42707 1.07296C7.45035 1.09618 7.46882 1.12377 7.48143 1.15414C7.49403 1.18451 7.50052 1.21707 7.50052 1.24996C7.50052 1.28284 7.49403 1.3154 7.48143 1.34578C7.46882 1.37615 7.45035 1.40374 7.42707 1.42696L1.92707 6.92696C1.88013 6.9739 1.81646 7.00027 1.75007 7.00027C1.68368 7.00027 1.62001 6.9739 1.57307 6.92696C1.52613 6.88002 1.49976 6.81635 1.49976 6.74996C1.49976 6.68357 1.52613 6.6199 1.57307 6.57296L7.07307 1.07296C7.09629 1.04968 7.12388 1.03121 7.15425 1.0186C7.18463 1.006 7.21719 0.999512 7.25007 0.999512C7.28296 0.999512 7.31552 1.006 7.34589 1.0186C7.37626 1.03121 7.40385 1.04968 7.42707 1.07296Z" fill="#6B7280"/>
                                    <path fill-rule="evenodd" clip-rule="evenodd" d="M1.57296 1.07296C1.54968 1.09618 1.53121 1.12377 1.5186 1.15414C1.506 1.18451 1.49951 1.21707 1.49951 1.24996C1.49951 1.28284 1.506 1.3154 1.5186 1.34578C1.53121 1.37615 1.54968 1.40374 1.57296 1.42696L7.07296 6.92696C7.1199 6.9739 7.18357 7.00027 7.24996 7.00027C7.31635 7.00027 7.38002 6.9739 7.42696 6.92696C7.4739 6.88002 7.50027 6.81635 7.50027 6.74996C7.50027 6.68357 7.4739 6.6199 7.42696 6.57296L1.92696 1.07296C1.90374 1.04968 1.87615 1.03121 1.84578 1.0186C1.8154 1.006 1.78284 0.999512 1.74996 0.999512C1.71707 0.999512 1.68451 1.006 1.65414 1.0186C1.62377 1.03121 1.59618 1.04968 1.57296 1.07296Z" fill="#6B7280"/>
                                </svg>
                            </div>
                        </div>

                        <div class="text-6 ml-8">...</div>
                        
                        <div class="select-page cur-pointer">
                            <div class="text-6 ml-16">Выбрать</div>
                            <svg class="ml-10" width="14" height="8" viewBox="0 0 14 8" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" clip-rule="evenodd" d="M0.645917 0.646039C0.692363 0.599476 0.747539 0.562533 0.808284 0.537326C0.869029 0.51212 0.93415 0.499146 0.999917 0.499146C1.06568 0.499146 1.13081 0.51212 1.19155 0.537326C1.2523 0.562533 1.30747 0.599476 1.35392 0.646039L6.99992 6.29304L12.6459 0.646039C12.6924 0.599551 12.7476 0.562675 12.8083 0.537516C12.8691 0.512357 12.9342 0.499407 12.9999 0.499407C13.0657 0.499407 13.1308 0.512357 13.1915 0.537516C13.2522 0.562675 13.3074 0.599551 13.3539 0.646039C13.4004 0.692527 13.4373 0.747716 13.4624 0.808455C13.4876 0.869195 13.5005 0.934295 13.5005 1.00004C13.5005 1.06578 13.4876 1.13088 13.4624 1.19162C13.4373 1.25236 13.4004 1.30755 13.3539 1.35404L7.35392 7.35404C7.30747 7.4006 7.2523 7.43754 7.19155 7.46275C7.13081 7.48796 7.06568 7.50093 6.99992 7.50093C6.93415 7.50093 6.86903 7.48796 6.80828 7.46275C6.74754 7.43754 6.69236 7.4006 6.64592 7.35404L0.645917 1.35404C0.599354 1.30759 0.562411 1.25242 0.537205 1.19167C0.511998 1.13093 0.499023 1.06581 0.499023 1.00004C0.499023 0.934272 0.511998 0.869151 0.537205 0.808405C0.562411 0.74766 0.599354 0.692485 0.645917 0.646039Z" fill="#6B7280"/>
                            </svg>

                        </div>
                    </div>
                </div>

                

                
                <div class="blue-box a-c cntr-row j-c text-white mt-15 cur-pointer">Сохранить</div>
                        

                    
                
            </div>
        </div>
    </div>
</template>

<script>

import PartLeft from './PartLeft.vue'

export default {
    name: 'AddUser',
    data() {
        return {
            accounts: [
                {id: 1, src: 'MyTarget', email: 'dsg@mail.ru', date: '12.03.2023', is_actual: 'Неактуален'},
                {id: 2, src: 'MyTarget', email: 'dsg@mail.ru', date: '12.03.2023', is_actual: 'Неактуален'}
            ]
        }
    },
    components: {
        'part-left': PartLeft
    }
}



</script>

<style scoped>
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

.input-user-name {
    display: flex;
    flex-direction: row;
    align-items: center;
    padding: 0px;

    width: 384px;
    height: 46px;

    background: #F2F7FF;
    border: 1px solid #E5E7EB;
    /* Drop Shadow/sm */

    box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.05);
    border-radius: 6px;
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
    padding-left: 26px;
    padding-top: 21px;
    padding-right: 27px;
}

.cntr-bg-2 {
    background: #FFFFFF;
    width: 70%;
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