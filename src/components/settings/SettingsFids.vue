<template>
    <modal-issave v-show="show_modal_is_save" />
    <div class="cntr-row">
        <part-left />



        <div class="cntr-bg-2">
            <div v-show="show_modal_is_save" class="pseudo_bg"></div>


            <div class="text-1">Настройка отправки фидов в сетях</div>
            <div class="line mt-10">
            </div>


            <!-- MENU -->
            <div class="cntr-row mt-18">

                <div class="cntr-row a-c">
                    <div class="menu_net grey-box h-40 cntr-row a-c pos-rel cur-pointer"
                        v-on:mouseover="show_selecter = true" v-on:mouseleave="show_selecter = false">

                        <svg class="ml-16" width="16" height="14" viewBox="0 0 16 14" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path d="M14.6668 1H1.3335L6.66683 7.30667V11.6667L9.3335 13V7.30667L14.6668 1Z"
                                stroke="#6B7280" stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round" />
                        </svg>

                        <div class="text-2 ml-11">Сеть</div>

                        <svg class="ml-14" width="12" height="8" viewBox="0 0 12 8" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M6.30969 6.93476C6.26905 6.9755 6.22077 7.00783 6.16762 7.02988C6.11446 7.05194 6.05748 7.06329 5.99994 7.06329C5.94239 7.06329 5.88541 7.05194 5.83226 7.02988C5.77911 7.00783 5.73083 6.9755 5.69019 6.93476L0.440187 1.68476C0.358037 1.60261 0.311884 1.49119 0.311884 1.37501C0.311884 1.25883 0.358037 1.14741 0.440187 1.06526C0.522337 0.98311 0.633758 0.936958 0.749938 0.936958C0.866116 0.936958 0.977537 0.98311 1.05969 1.06526L5.99994 6.00639L10.9402 1.06526C11.0223 0.983111 11.1338 0.936959 11.2499 0.936959C11.3661 0.936959 11.4775 0.983111 11.5597 1.06526C11.6418 1.14741 11.688 1.25883 11.688 1.37501C11.688 1.49119 11.6418 1.60261 11.5597 1.68476L6.30969 6.93476Z"
                                fill="#374151" />
                        </svg>

                        <selecter-net v-if="show_selecter" v-on:mouseover="show_selecter = true"
                            v-on:mouseleave="show_selecter = false" />
                    </div>

                    <div class="menu_index grey-box menu_item_padding h-40 cntr-row a-c pos-rel cur-pointer ml-8"
                        v-on:mouseover="show_selecter_index = true" v-on:mouseleave="show_selecter_index = false">

                        <svg width="16" height="14" viewBox="0 0 16 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M14.6668 1H1.3335L6.66683 7.30667V11.6667L9.3335 13V7.30667L14.6668 1Z"
                                stroke="#6B7280" stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round" />
                        </svg>

                        <div class="text-2 ml-11">Индекс</div>

                        <svg class="ml-14" width="12" height="8" viewBox="0 0 12 8" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M6.30969 6.93476C6.26905 6.9755 6.22077 7.00783 6.16762 7.02988C6.11446 7.05194 6.05748 7.06329 5.99994 7.06329C5.94239 7.06329 5.88541 7.05194 5.83226 7.02988C5.77911 7.00783 5.73083 6.9755 5.69019 6.93476L0.440187 1.68476C0.358037 1.60261 0.311884 1.49119 0.311884 1.37501C0.311884 1.25883 0.358037 1.14741 0.440187 1.06526C0.522337 0.98311 0.633758 0.936958 0.749938 0.936958C0.866116 0.936958 0.977537 0.98311 1.05969 1.06526L5.99994 6.00639L10.9402 1.06526C11.0223 0.983111 11.1338 0.936959 11.2499 0.936959C11.3661 0.936959 11.4775 0.983111 11.5597 1.06526C11.6418 1.14741 11.688 1.25883 11.688 1.37501C11.688 1.49119 11.6418 1.60261 11.5597 1.68476L6.30969 6.93476Z"
                                fill="#374151" />
                        </svg>

                        <select-index v-if="show_selecter_index" v-on:mouseover="show_selecter_index = true"
                            v-on:mouseleave="show_selecter_index = false" />
                    </div>
                </div>


                <div v-show="is_check" class="menu_save h-40 cntr-row a-c pos-rel cur-pointer">

                    <svg width="17" height="17" viewBox="0 0 17 17" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <g clip-path="url(#clip0_44_102799)">
                            <path
                                d="M15.483 7.41359V8.02693C15.4822 9.46454 15.0167 10.8634 14.1559 12.0148C13.2951 13.1662 12.0852 14.0086 10.7066 14.4162C9.32795 14.8238 7.8545 14.7749 6.50597 14.2767C5.15745 13.7784 4.00609 12.8577 3.22363 11.6516C2.44117 10.4456 2.06952 9.01897 2.16411 7.58447C2.2587 6.14997 2.81446 4.78448 3.74851 3.69164C4.68256 2.59881 5.94485 1.83718 7.34712 1.52036C8.74939 1.20353 10.2165 1.34849 11.5297 1.93359"
                                stroke="#6B7280" stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round" />
                            <path d="M15.4831 2.69434L8.81641 9.36767L6.81641 7.36767" stroke="#6B7280"
                                stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round" />
                        </g>
                        <defs>
                            <clipPath id="clip0_44_102799">
                                <rect width="16" height="16" fill="white" transform="translate(0.816406 0.0273438)" />
                            </clipPath>
                        </defs>
                    </svg>


                    <div class="text-2 ml-11">Сохранить</div>


                </div>
            </div>

            <!-- TABLE -->
            <div class="cntr-table">
                <table class="scroll_table">
                    <tr class="header1">
                        <th></th>
                        <th></th>
                        <th colspan="3">BK</th>
                        <th colspan="2">BKP</th>
                        <th colspan="3">MyTarget</th>
                    </tr>
                    <tr class="header2">
                        <th @click="is_sorted_index = !is_sorted_index" :class="{ color2: is_sorted_index }">
                            Индекс
                            <span v-show="is_sorted_index" class="arrow_sort">
                                <svg width="16" height="16" viewBox="0 0 16 16" fill="none"
                                    xmlns="http://www.w3.org/2000/svg">
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M8.00014 11.9999C8.13275 11.9999 8.25993 11.9472 8.3537 11.8535C8.44747 11.7597 8.50014 11.6325 8.50014 11.4999V5.70692L10.6461 7.85392C10.6926 7.90041 10.7478 7.93728 10.8086 7.96244C10.8693 7.9876 10.9344 8.00055 11.0001 8.00055C11.0659 8.00055 11.131 7.9876 11.1917 7.96244C11.2525 7.93728 11.3077 7.90041 11.3541 7.85392C11.4006 7.80743 11.4375 7.75224 11.4627 7.6915C11.4878 7.63076 11.5008 7.56566 11.5008 7.49992C11.5008 7.43417 11.4878 7.36907 11.4627 7.30833C11.4375 7.24759 11.4006 7.19241 11.3541 7.14592L8.35414 4.14592C8.3077 4.09935 8.25252 4.06241 8.19178 4.0372C8.13103 4.012 8.06591 3.99902 8.00014 3.99902C7.93438 3.99902 7.86926 4.012 7.80851 4.0372C7.74776 4.06241 7.69259 4.09935 7.64614 4.14592L4.64614 7.14592C4.55226 7.2398 4.49951 7.36714 4.49951 7.49992C4.49951 7.63269 4.55226 7.76003 4.64614 7.85392C4.74003 7.9478 4.86737 8.00055 5.00014 8.00055C5.13292 8.00055 5.26026 7.9478 5.35414 7.85392L7.50014 5.70692L7.50014 11.4999C7.50014 11.6325 7.55282 11.7597 7.64659 11.8535C7.74036 11.9472 7.86754 11.9999 8.00014 11.9999Z"
                                        fill="#006AFF" />
                                </svg>
                            </span>
                        </th>
                        <th @click="is_sorted_active_deliver = !is_sorted_active_deliver" :class="{ color2: is_sorted_active_deliver }">
                            Активных доставок
                            <span v-show="is_sorted_active_deliver" class="arrow_sort">
                                <svg width="16" height="16" viewBox="0 0 16 16" fill="none"
                                    xmlns="http://www.w3.org/2000/svg">
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M8.00014 11.9999C8.13275 11.9999 8.25993 11.9472 8.3537 11.8535C8.44747 11.7597 8.50014 11.6325 8.50014 11.4999V5.70692L10.6461 7.85392C10.6926 7.90041 10.7478 7.93728 10.8086 7.96244C10.8693 7.9876 10.9344 8.00055 11.0001 8.00055C11.0659 8.00055 11.131 7.9876 11.1917 7.96244C11.2525 7.93728 11.3077 7.90041 11.3541 7.85392C11.4006 7.80743 11.4375 7.75224 11.4627 7.6915C11.4878 7.63076 11.5008 7.56566 11.5008 7.49992C11.5008 7.43417 11.4878 7.36907 11.4627 7.30833C11.4375 7.24759 11.4006 7.19241 11.3541 7.14592L8.35414 4.14592C8.3077 4.09935 8.25252 4.06241 8.19178 4.0372C8.13103 4.012 8.06591 3.99902 8.00014 3.99902C7.93438 3.99902 7.86926 4.012 7.80851 4.0372C7.74776 4.06241 7.69259 4.09935 7.64614 4.14592L4.64614 7.14592C4.55226 7.2398 4.49951 7.36714 4.49951 7.49992C4.49951 7.63269 4.55226 7.76003 4.64614 7.85392C4.74003 7.9478 4.86737 8.00055 5.00014 8.00055C5.13292 8.00055 5.26026 7.9478 5.35414 7.85392L7.50014 5.70692L7.50014 11.4999C7.50014 11.6325 7.55282 11.7597 7.64659 11.8535C7.74036 11.9472 7.86754 11.9999 8.00014 11.9999Z"
                                        fill="#006AFF" />
                                </svg>
                            </span>
                        </th>
                        <th>Статья</th>
                        <th>Прерол</th>
                        <th>Пост</th>
                        <th>Статья</th>
                        <th>Пост</th>
                        <th>Статья</th>
                        <th>Прерол</th>
                        <th>Пост</th>
                    </tr>

                    <tr v-for="q in [30, 36, 25, 80, 45, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1]" v-bind:key="q">
                        <th>Индекс</th>
                        <th>{{ q }}</th>
                        <td @click="is_check = !is_check">
                            <svg-check />
                            <svg class="svg_check" v-show="is_check && q === 30" width="10" height="8" viewBox="0 0 10 8"
                                fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path
                                    d="M3.5775 7.1675C3.3775 7.1675 3.1875 7.0875 3.0475 6.9475L0.2175 4.1175C-0.0725 3.8275 -0.0725 3.3475 0.2175 3.0575C0.5075 2.7675 0.9875 2.7675 1.2775 3.0575L3.5775 5.3575L8.7175 0.2175C9.0075 -0.0725 9.4875 -0.0725 9.7775 0.2175C10.0675 0.5075 10.0675 0.987499 9.7775 1.2775L4.1075 6.9475C3.9675 7.0875 3.7775 7.1675 3.5775 7.1675Z"
                                    fill="#6B7280" />
                            </svg>

                        </td>
                        <td><svg-check /></td>
                        <td><svg-check /></td>
                        <td><svg-check /></td>
                        <td><svg-check /></td>
                        <td><svg-check /></td>
                        <td><svg-check /></td>
                        <td><svg-check /></td>
                    </tr>
                </table>
            </div>

            <div class="cntr-row j-b a-c mt-168">
                <div class="cntr-row">
                    <div class="grey-box w-97 h-40 cntr-row a-c">
                        <svg class="ml-16" width="8" height="14" viewBox="0 0 8 14" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M7.35404 0.646009C7.4006 0.692455 7.43754 0.74763 7.46275 0.808375C7.48796 0.86912 7.50093 0.934242 7.50093 1.00001C7.50093 1.06578 7.48796 1.1309 7.46275 1.19164C7.43754 1.25239 7.4006 1.30756 7.35404 1.35401L1.70704 7.00001L7.35404 12.646C7.44793 12.7399 7.50067 12.8672 7.50067 13C7.50067 13.1328 7.44793 13.2601 7.35404 13.354C7.26015 13.4479 7.13281 13.5006 7.00004 13.5006C6.86726 13.5006 6.73993 13.4479 6.64604 13.354L0.646039 7.35401C0.599476 7.30756 0.562533 7.25239 0.537326 7.19164C0.51212 7.1309 0.499146 7.06578 0.499146 7.00001C0.499146 6.93424 0.51212 6.86912 0.537326 6.80838C0.562533 6.74763 0.599476 6.69245 0.646039 6.64601L6.64604 0.646009C6.69248 0.599446 6.74766 0.562503 6.80841 0.537296C6.86915 0.51209 6.93427 0.499115 7.00004 0.499115C7.06581 0.499115 7.13093 0.51209 7.19167 0.537296C7.25242 0.562503 7.30759 0.599446 7.35404 0.646009Z"
                                fill="#6B7280" />
                        </svg>
                        <div class="text-2 ml-11">Назад</div>
                    </div>

                    <div class="num-page-box num-page-txt a-c cntr-row j-c">1</div>

                    <div class="blue-box a-c cntr-row j-c text-white ml-10">2</div>

                    <div class="num-page-box num-page-txt a-c cntr-row j-c">3</div>

                    <div class="num-page-box num-page-txt a-c cntr-row j-c">4</div>

                    <div class="num-page-box num-page-txt a-c cntr-row j-c">5</div>

                    <div class="grey-box w-98 h-40 cntr-row a-c ml-10 btn_onwards cur-pointer">

                        <div class="text-2 ml-16 ">Далее</div>

                        <svg class="ml-11" width="8" height="14" viewBox="0 0 8 14" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M0.646039 0.646009C0.692485 0.599446 0.74766 0.562503 0.808405 0.537296C0.869151 0.51209 0.934272 0.499115 1.00004 0.499115C1.06581 0.499115 1.13093 0.51209 1.19167 0.537296C1.25242 0.562503 1.30759 0.599446 1.35404 0.646009L7.35404 6.64601C7.4006 6.69245 7.43754 6.74763 7.46275 6.80838C7.48796 6.86912 7.50093 6.93424 7.50093 7.00001C7.50093 7.06578 7.48796 7.1309 7.46275 7.19164C7.43754 7.25239 7.4006 7.30756 7.35404 7.35401L1.35404 13.354C1.26015 13.4479 1.13281 13.5006 1.00004 13.5006C0.867263 13.5006 0.739926 13.4479 0.646039 13.354C0.552152 13.2601 0.499407 13.1328 0.499407 13C0.499407 12.8672 0.552152 12.7399 0.646039 12.646L6.29304 7.00001L0.646039 1.35401C0.599476 1.30756 0.562533 1.25239 0.537326 1.19164C0.51212 1.1309 0.499146 1.06578 0.499146 1.00001C0.499146 0.934242 0.51212 0.86912 0.537326 0.808375C0.562533 0.74763 0.599476 0.692455 0.646039 0.646009Z"
                                fill="#6B7280" />
                        </svg>
                    </div>
                </div>

                <div class="cntr-row a-c">
                    <div class="text-2">Показать</div>
                    <div class="grey-box w-113 h-40 cntr-row a-c j-b ml-11">

                        <div class="text-2 ml-11">10</div>

                        <svg class="mr-16" width="12" height="8" viewBox="0 0 12 8" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M6.30969 6.93476C6.26905 6.9755 6.22077 7.00783 6.16762 7.02988C6.11446 7.05194 6.05748 7.06329 5.99994 7.06329C5.94239 7.06329 5.88541 7.05194 5.83226 7.02988C5.77911 7.00783 5.73083 6.9755 5.69019 6.93476L0.440187 1.68476C0.358037 1.60261 0.311884 1.49119 0.311884 1.37501C0.311884 1.25883 0.358037 1.14741 0.440187 1.06526C0.522337 0.98311 0.633758 0.936958 0.749938 0.936958C0.866116 0.936958 0.977537 0.98311 1.05969 1.06526L5.99994 6.00639L10.9402 1.06526C11.0223 0.983111 11.1338 0.936959 11.2499 0.936959C11.3661 0.936959 11.4775 0.983111 11.5597 1.06526C11.6418 1.14741 11.688 1.25883 11.688 1.37501C11.688 1.49119 11.6418 1.60261 11.5597 1.68476L6.30969 6.93476Z"
                                fill="#374151" />
                        </svg>

                    </div>
                </div>
            </div>

        </div>
    </div>
</template>

<script>

import PartLeftListDelivers from '../delivers/PartLeftListDelivers.vue'
import SvgFidcheck from '../svg/SvgFidcheck'
import ModalIssave from './ModalIsSave.vue'
import SelecterNet from '../SelecterNet'
import SelecterIndex from '../SelecterIndex.vue'

export default {
    name: 'SettingsFids',
    data() {
        return {

            is_check: true,
            show_modal_is_save: false,
            show_selecter: false,
            show_selecter_index: false,
            is_sorted_active_deliver: false,
            is_sorted_index: false
        }
    },
    components: {
        'part-left': PartLeftListDelivers,
        'svg-check': SvgFidcheck,
        'modal-issave': ModalIssave,
        'selecter-net': SelecterNet,
        'select-index': SelecterIndex
    }
}



</script>

<style scoped>
.arrow_sort {
    position: absolute;
    top: 50%;
    transform: translateY(-40%);
    right: 80px;
}

.color2 {
    color: #3B82F6;
}

.pseudo_bg {
    top: 0;
    left: 0;
    position: absolute;
    width: 100%;
    height: 100%;
    background: #6B7280;
    opacity: 0.5;
    background-blend-mode: multiply;
    z-index: 12;
}

.btn_onwards:hover {
    background: var(--d-9-d-9-d-9, #F3F4F6);
    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);
}

.menu_net {
    /* padding-right: 13px; */
    width: 106px;
}

.menu_save {
    padding-left: 17px;
    /* padding-right: 17px; */
    border-radius: 5.224px;
    border: 0.871px solid var(--gray-200, #E5E7EB);
    background: var(--d-9-d-9-d-9, #F3F4F6);
    width: 128px;
    margin-left: 50vw;
}

.menu_index {
    width: 105px;
}

.svg_check {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translateY(-50%) translateX(-50%);
    /* transform: translateX(-50%); */
}

.menu_index:hover {
    background: var(--d-9-d-9-d-9, #F2F7FF);

    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);
}

::-webkit-scrollbar {
    width: 6px;
}

/* Track */
/* ::-webkit-scrollbar-track {
  background: #f1f1f1;
} */

/* Handle */
::-webkit-scrollbar-thumb {
    border-radius: 999px;
    background: var(--gray-200, #E5E7EB);
}

.mt-168 {
    margin-top: 28px;
}

.cntr-table {
    margin-top: 21px;
    padding-right: 27px;
    overflow: scroll;
    width: 75vw;
    height: 70vh;
    position: relative;
}


/* TABLES */

td {
    border: 1px solid var(--gray-200, #E5E7EB);
    position: relative;
    height: 44px;
    width: 100px;
}

.header1 {
    position: sticky;
    top: 0;
    background-color: #fff;
    z-index: 11;
    border: 1px solid var(--gray-200, #E5E7EB);
}

.header2 {
    position: sticky;
    top: 50px;
    background-color: #fff;
    z-index: 11;
    border: 1px solid var(--gray-200, #E5E7EB);
}



th {
    border: 1px solid var(--gray-200, #E5E7EB);

    color: var(--gray-500, #6B7280);

    /* XS/Medium */
    font-family: Inter;
    font-size: 12px;
    font-style: normal;
    font-weight: 500;
    line-height: 16px;
    /* 133.333% */
    letter-spacing: 0.06px;
}

/* th:first-child { */
tr:nth-child(n + 1) th:first-child {
    position: sticky;
    left: 0;
    width: 210px;
    background-color: #fff;
    z-index: 10;
    text-align: left;
    padding-left: 20px;
}

tr:nth-child(n + 1) th:nth-child(2) {
    position: sticky;
    left: 210px;
    width: 210px;
    background-color: #fff;
    z-index: 10;

    text-align: left;
}

tr:nth-child(n + 3) th:nth-child(1) {
    color: var(--gray-800, #1F2937);

    /* SM/Medium */
    font-family: Inter;
    font-size: 14px;
    font-style: normal;
    font-weight: 500;
    line-height: 20px;
    /* 142.857% */
    letter-spacing: 0.07px;
}
tr:nth-child(n + 3) th:nth-child(2) {
    color: var(--gray-800, #1F2937);

    /* SM/Medium */
    font-family: Inter;
    font-size: 14px;
    font-style: normal;
    font-weight: 500;
    line-height: 20px;
    /* 142.857% */
    letter-spacing: 0.07px;
    text-align: left;
    padding-left: 20px;
}

tr:nth-child(2) th:nth-child(2):hover {

    border-right: 1px solid var(--gray-200, #E5E7EB);
    background: var(--d-9-d-9-d-9, #F3F4F6);

    cursor: pointer;
}

tr:nth-child(2) th:nth-child(1):hover {

border-right: 1px solid var(--gray-200, #E5E7EB);
background: var(--d-9-d-9-d-9, #F3F4F6);

cursor: pointer;
}

tr:first-child th {
    height: 33px;
    padding: 12px 20px;
}

tr:nth-child(2) th {
    height: 22px;
    padding: 12px 20px;
}


table {
    margin-top: 18px;
    border-collapse: collapse;
    width: 1300px;
}





.w-98 {
    width: 98px;
}

.ml-10 {
    margin-left: 10px;
}

.text-white {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
    /* identical to box height, or 150% */

    text-align: center;
    letter-spacing: 0.005em;

    /* White/White */

    color: #FFFFFF;
}

.j-c {
    justify-content: center;
}

.num-page-txt {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
    /* identical to box height, or 150% */

    text-align: center;
    letter-spacing: 0.005em;

    color: #6B7280;
}

.num-page-box {
    width: 40px;
    height: 40px;

    background: #FFFFFF;
    border-radius: 6px;
}

.blue-box {
    width: 40px;
    height: 40px;

    /* Blue/500 */

    background: #3B82F6;
    border-radius: 6px;
}

.j-b {
    justify-content: space-between;
}

.w-97 {
    width: 97px;
}

.mt-20 {
    margin-top: 20px;
}

.mr-16 {
    margin-right: 16px;
}



.ml-8 {
    margin-left: 8px;
}

.menu_item_padding {
    padding: 0px 16px 0px 16px;
}

.grey-box {
    border: 1px solid #E5E7EB;
    /* Drop Shadow/sm */

    box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.05);
    border-radius: 6px;
}

.w-113 {
    width: 113px;
}

.h-40 {
    height: 40px
}

.a-c {
    align-items: center;
}

.pos-rel {
    position: relative;
}

.cur-pointer {
    cursor: pointer;
}

.ml-16 {
    margin-left: 16px;
}

.ml-11 {
    margin-left: 11px;
}

.mt-18 {
    margin-top: 18px;
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

.ml-14 {
    margin-left: 14px;
}

.line {
    height: 1px;

    background: #E5E7EB;
}

.mt-10 {
    margin-top: 10px;
}



.cntr-bg-2 {
    background: #FFFFFF;
    position: relative;
    height: calc(100vh - 20px);
    overflow: hidden;
    /* width: 70%; */

    padding-top: 20px;
    padding-left: 40px;
}

.cntr-row {
    display: flex;
    position: relative;
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
}</style>