<template>
    <modal-issave v-show="show_modal_is_save" :show_modal_is_save="show_modal_is_save" />
    <div class="cntr-row">
        <part-left />



        <div class="cntr-bg-2">
            <div v-show="show_modal_is_save" class="pseudo_bg"></div>


            <div class="text-1">Настройка лимитов, ставок и моделей закупки для ВК, ВКР и МТ</div>
            <div class="line mt-10">
            </div>


            <!-- MENU -->
            <div class="cntr-row mt-18 pos-rel">

                <div class="cntr-row a-c">

                    <div @click="is_selected_index = !is_selected_index"
                        class="menu_index grey-box menu_item_padding h-40 cntr-row a-c pos-rel cur-pointer"
                        v-on:mouseover="show_selecter_index = true" v-on:mouseleave="show_selecter_index = false">

                        <svg v-show="is_selected_index" width="16" height="14" viewBox="0 0 16 14" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path d="M14.6668 1H1.3335L6.66683 7.30667V11.6667L9.3335 13V7.30667L14.6668 1Z"
                                stroke="#6B7280" stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round" />
                        </svg>
                        <svg v-show="!is_selected_index" width="16" height="14" viewBox="0 0 16 14" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path d="M14.6668 1H1.3335L6.66683 7.30667V11.6667L9.3335 13V7.30667L14.6668 1Z"
                                stroke="#3B82F6" stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round" />
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


                <div v-show="is_settings_mode" class="limits_menu_save h-40" @click="() => {
                    is_settings_mode = !is_settings_mode
                    show_modal_is_save = true
                }">

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



                <div class="grey-box cntr-row a-c menu_settings pos-rel cur-pointer"
                    @click="is_settings_mode = !is_settings_mode">
                    <svg width="20" height="21" viewBox="0 0 20 21" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <g clip-path="url(#clip0_290_64570)">
                            <path
                                d="M9.81643 12.8335C11.1389 12.8335 12.211 11.7615 12.211 10.439C12.211 9.11651 11.1389 8.04443 9.81643 8.04443C8.49396 8.04443 7.42188 9.11651 7.42188 10.439C7.42188 11.7615 8.49396 12.8335 9.81643 12.8335Z"
                                stroke="#6B7280" stroke-width="1.47357" stroke-linecap="round" stroke-linejoin="round" />
                            <path
                                d="M15.7232 12.8338C15.617 13.0745 15.5853 13.3416 15.6322 13.6005C15.6792 13.8594 15.8026 14.0984 15.9866 14.2865L16.0345 14.3344C16.183 14.4826 16.3007 14.6587 16.381 14.8525C16.4614 15.0463 16.5027 15.254 16.5027 15.4638C16.5027 15.6736 16.4614 15.8813 16.381 16.0751C16.3007 16.2689 16.183 16.445 16.0345 16.5932C15.8863 16.7417 15.7102 16.8594 15.5164 16.9397C15.3226 17.0201 15.1149 17.0614 14.9051 17.0614C14.6953 17.0614 14.4876 17.0201 14.2938 16.9397C14.1 16.8594 13.9239 16.7417 13.7757 16.5932L13.7278 16.5453C13.5397 16.3613 13.3007 16.2379 13.0418 16.1909C12.7829 16.144 12.5158 16.1757 12.2751 16.2819C12.039 16.3831 11.8377 16.5511 11.6958 16.7653C11.554 16.9794 11.4779 17.2304 11.4769 17.4872V17.6229C11.4769 18.0463 11.3087 18.4523 11.0093 18.7517C10.7099 19.0511 10.3039 19.2193 9.88052 19.2193C9.45714 19.2193 9.05109 19.0511 8.75172 18.7517C8.45234 18.4523 8.28415 18.0463 8.28415 17.6229V17.5511C8.27797 17.2869 8.19245 17.0306 8.03872 16.8157C7.88498 16.6007 7.67013 16.437 7.42211 16.3458C7.18136 16.2395 6.91431 16.2079 6.65538 16.2548C6.39645 16.3018 6.15753 16.4252 5.96941 16.6092L5.92152 16.6571C5.77326 16.8055 5.5972 16.9233 5.4034 17.0036C5.2096 17.0839 5.00187 17.1253 4.79209 17.1253C4.5823 17.1253 4.37457 17.0839 4.18077 17.0036C3.98697 16.9233 3.81091 16.8055 3.66265 16.6571C3.51423 16.5088 3.39648 16.3328 3.31614 16.139C3.23581 15.9452 3.19446 15.7374 3.19446 15.5277C3.19446 15.3179 3.23581 15.1101 3.31614 14.9163C3.39648 14.7225 3.51423 14.5465 3.66265 14.3982L3.71054 14.3503C3.89455 14.1622 4.01799 13.9233 4.06494 13.6644C4.11189 13.4054 4.0802 13.1384 3.97395 12.8976C3.87276 12.6616 3.70476 12.4602 3.49062 12.3184C3.27647 12.1766 3.02553 12.1005 2.76868 12.0995H2.63299C2.20961 12.0995 1.80357 11.9313 1.50419 11.6319C1.20481 11.3325 1.03662 10.9265 1.03662 10.5031C1.03662 10.0797 1.20481 9.67365 1.50419 9.37427C1.80357 9.0749 2.20961 8.90671 2.63299 8.90671H2.70483C2.96902 8.90053 3.22525 8.81501 3.4402 8.66127C3.65514 8.50754 3.81887 8.29269 3.91009 8.04467C4.01634 7.80392 4.04804 7.53687 4.00109 7.27794C3.95414 7.01901 3.8307 6.78008 3.64669 6.59197L3.5988 6.54408C3.45037 6.39582 3.33263 6.21976 3.25229 6.02596C3.17195 5.83216 3.1306 5.62443 3.1306 5.41464C3.1306 5.20486 3.17195 4.99713 3.25229 4.80333C3.33263 4.60953 3.45037 4.43347 3.5988 4.28521C3.74706 4.13679 3.92312 4.01904 4.11692 3.9387C4.31071 3.85837 4.51844 3.81702 4.72823 3.81702C4.93802 3.81702 5.14575 3.85837 5.33955 3.9387C5.53334 4.01904 5.7094 4.13679 5.85766 4.28521L5.90555 4.3331C6.09367 4.51711 6.3326 4.64055 6.59152 4.6875C6.85045 4.73445 7.11751 4.70275 7.35825 4.5965H7.42211C7.65819 4.49532 7.85953 4.32732 8.00135 4.11317C8.14316 3.89903 8.21927 3.64809 8.22029 3.39124V3.25555C8.22029 2.83217 8.38848 2.42612 8.68786 2.12675C8.98724 1.82737 9.39328 1.65918 9.81667 1.65918C10.24 1.65918 10.6461 1.82737 10.9455 2.12675C11.2448 2.42612 11.413 2.83217 11.413 3.25555V3.32739C11.4141 3.58423 11.4902 3.83517 11.632 4.04932C11.7738 4.26347 11.9751 4.43147 12.2112 4.53265C12.452 4.6389 12.719 4.67059 12.978 4.62365C13.2369 4.5767 13.4758 4.45326 13.6639 4.26925L13.7118 4.22136C13.8601 4.07293 14.0361 3.95518 14.2299 3.87485C14.4237 3.79451 14.6315 3.75316 14.8412 3.75316C15.051 3.75316 15.2588 3.79451 15.4526 3.87485C15.6464 3.95518 15.8224 4.07293 15.9707 4.22136C16.1191 4.36962 16.2369 4.54568 16.3172 4.73947C16.3975 4.93327 16.4389 5.141 16.4389 5.35079C16.4389 5.56058 16.3975 5.76831 16.3172 5.9621C16.2369 6.1559 16.1191 6.33196 15.9707 6.48022L15.9228 6.52811C15.7388 6.71623 15.6153 6.95516 15.5684 7.21408C15.5214 7.47301 15.5531 7.74007 15.6594 7.98081V8.04467C15.7606 8.28075 15.9286 8.48209 16.1427 8.6239C16.3569 8.76572 16.6078 8.84183 16.8646 8.84285H17.0003C17.4237 8.84285 17.8298 9.01104 18.1291 9.31042C18.4285 9.6098 18.5967 10.0158 18.5967 10.4392C18.5967 10.8626 18.4285 11.2687 18.1291 11.568C17.8298 11.8674 17.4237 12.0356 17.0003 12.0356H16.9285C16.6717 12.0366 16.4207 12.1127 16.2066 12.2545C15.9924 12.3964 15.8244 12.5977 15.7232 12.8338V12.8338Z"
                                stroke="#6B7280" stroke-width="1.47357" stroke-linecap="round" stroke-linejoin="round" />
                        </g>
                        <defs>
                            <clipPath id="clip0_290_64570">
                                <rect width="19.1565" height="19.1565" fill="white"
                                    transform="translate(0.238281 0.86084)" />
                            </clipPath>
                        </defs>
                    </svg>


                    <div @click="show_modal = !show_modal" class=" text-2 ml-11 cur-pointer">Настроить</div>
                </div>
            </div>

            <!-- TABLE -->
            <div class="cntr-table">
                <table class="scroll_table">
                    <tr class="header1">
                        <th class="index_header cur-pointer" @click="is_sorted_index = !is_sorted_index"
                            :class="{ color2: is_sorted_index }">
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
                        <th @click="is_sorted_active_deliver = !is_sorted_active_deliver"
                            :class="{ color2: is_sorted_active_deliver }">
                            Настройка
                            <span v-show="is_sorted_active_deliver" class="arrow_sort">
                                <svg width="16" height="16" viewBox="0 0 16 16" fill="none"
                                    xmlns="http://www.w3.org/2000/svg">
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M8.00014 11.9999C8.13275 11.9999 8.25993 11.9472 8.3537 11.8535C8.44747 11.7597 8.50014 11.6325 8.50014 11.4999V5.70692L10.6461 7.85392C10.6926 7.90041 10.7478 7.93728 10.8086 7.96244C10.8693 7.9876 10.9344 8.00055 11.0001 8.00055C11.0659 8.00055 11.131 7.9876 11.1917 7.96244C11.2525 7.93728 11.3077 7.90041 11.3541 7.85392C11.4006 7.80743 11.4375 7.75224 11.4627 7.6915C11.4878 7.63076 11.5008 7.56566 11.5008 7.49992C11.5008 7.43417 11.4878 7.36907 11.4627 7.30833C11.4375 7.24759 11.4006 7.19241 11.3541 7.14592L8.35414 4.14592C8.3077 4.09935 8.25252 4.06241 8.19178 4.0372C8.13103 4.012 8.06591 3.99902 8.00014 3.99902C7.93438 3.99902 7.86926 4.012 7.80851 4.0372C7.74776 4.06241 7.69259 4.09935 7.64614 4.14592L4.64614 7.14592C4.55226 7.2398 4.49951 7.36714 4.49951 7.49992C4.49951 7.63269 4.55226 7.76003 4.64614 7.85392C4.74003 7.9478 4.86737 8.00055 5.00014 8.00055C5.13292 8.00055 5.26026 7.9478 5.35414 7.85392L7.50014 5.70692L7.50014 11.4999C7.50014 11.6325 7.55282 11.7597 7.64659 11.8535C7.74036 11.9472 7.86754 11.9999 8.00014 11.9999Z"
                                        fill="#006AFF" />
                                </svg>
                            </span>
                        </th>
                        <th>ВК/ Реклама сайта</th>
                        <th>ВК/ ТГБ</th>
                        <th>ВК/ Универсальная запись</th>

                        <th>МТ/ Мультиформат</th>
                        <th>МТ/ Мультиформат сеть</th>
                        <th>МТ/ ТГБ</th>
                    </tr>

                    <template v-for="q in [1, 2, 3, 4, 5]" v-bind:key="q">
                        <tr>
                            <th rowspan="3">Индекс</th>
                            <th>Дневной лимит, руб.</th>
                            <td>
                                <div v-show="!is_settings_mode">500</div>
                                <input class="td_input" v-show="is_settings_mode" type="text" />
                            </td>
                            <td>500</td>
                            <td>100</td>
                            <td>500</td>
                            <td>500</td>
                            <td>100</td>
                        </tr>
                        <tr>
                            <th>Ставка, руб.</th>
                            <td>10</td>
                            <td>10</td>
                            <td>70</td>
                            <td>10</td>
                            <td>10</td>
                            <td>70</td>
                        </tr>
                        <tr>
                            <th>Модель закупки</th>
                            <td>CPC
                                <span @click="show_selecter_cpc = !show_selecter_cpc" v-show="is_settings_mode" class="td_chevron">
                                    <svg width="14" height="15" viewBox="0 0 14 15" fill="none"
                                        xmlns="http://www.w3.org/2000/svg">
                                        <path fill-rule="evenodd" clip-rule="evenodd"
                                            d="M6.69031 10.434C6.73095 10.4747 6.77923 10.507 6.83238 10.5291C6.88554 10.5511 6.94252 10.5625 7.00006 10.5625C7.05761 10.5625 7.11459 10.5511 7.16774 10.5291C7.22089 10.507 7.26917 10.4747 7.30981 10.434L12.5598 5.18397C12.642 5.10182 12.6881 4.9904 12.6881 4.87422C12.6881 4.75804 12.642 4.64662 12.5598 4.56447C12.4777 4.48232 12.3662 4.43617 12.2501 4.43617C12.1339 4.43617 12.0225 4.48232 11.9403 4.56447L7.00006 9.50559L2.05981 4.56447C1.97766 4.48232 1.86624 4.43617 1.75006 4.43617C1.63389 4.43617 1.52247 4.48232 1.44031 4.56447C1.35816 4.64662 1.31201 4.75804 1.31201 4.87422C1.31201 4.9904 1.35816 5.10182 1.44031 5.18397L6.69031 10.434Z"
                                            fill="#374151" />
                                    </svg>
                                </span>
                                <div v-show="q == 1 && is_settings_mode && show_selecter_cpc" class="cntr_selecter_cpc"><select-cpc/></div>
                            </td>
                            <td>CPM</td>
                            <td>CPM</td>
                            <td>CPC</td>
                            <td>CPM</td>
                            <td>CPM</td>
                        </tr>
                    </template>
                </table>
            </div>

            <div class="cntr-row j-b a-c mt-168">
                <div class="cntr-row">
                    <div class="grey-box w-97 h-40 cntr-row a-c">
                        <svg v-show="!is_settings_mode" class="ml-16" width="8" height="14" viewBox="0 0 8 14" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M7.35404 0.646009C7.4006 0.692455 7.43754 0.74763 7.46275 0.808375C7.48796 0.86912 7.50093 0.934242 7.50093 1.00001C7.50093 1.06578 7.48796 1.1309 7.46275 1.19164C7.43754 1.25239 7.4006 1.30756 7.35404 1.35401L1.70704 7.00001L7.35404 12.646C7.44793 12.7399 7.50067 12.8672 7.50067 13C7.50067 13.1328 7.44793 13.2601 7.35404 13.354C7.26015 13.4479 7.13281 13.5006 7.00004 13.5006C6.86726 13.5006 6.73993 13.4479 6.64604 13.354L0.646039 7.35401C0.599476 7.30756 0.562533 7.25239 0.537326 7.19164C0.51212 7.1309 0.499146 7.06578 0.499146 7.00001C0.499146 6.93424 0.51212 6.86912 0.537326 6.80838C0.562533 6.74763 0.599476 6.69245 0.646039 6.64601L6.64604 0.646009C6.69248 0.599446 6.74766 0.562503 6.80841 0.537296C6.86915 0.51209 6.93427 0.499115 7.00004 0.499115C7.06581 0.499115 7.13093 0.51209 7.19167 0.537296C7.25242 0.562503 7.30759 0.599446 7.35404 0.646009Z"
                                fill="#6B7280" />
                        </svg>
                        <svg v-show="is_settings_mode" class="ml-16" width="16" height="16" viewBox="0 0 16 16" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M11.3539 1.64689C11.4005 1.69334 11.4374 1.74852 11.4626 1.80926C11.4878 1.87001 11.5008 1.93513 11.5008 2.00089C11.5008 2.06666 11.4878 2.13178 11.4626 2.19253C11.4374 2.25327 11.4005 2.30845 11.3539 2.35489L5.70692 8.00089L11.3539 13.6469C11.4478 13.7408 11.5005 13.8681 11.5005 14.0009C11.5005 14.1337 11.4478 14.261 11.3539 14.3549C11.26 14.4488 11.1327 14.5015 10.9999 14.5015C10.8671 14.5015 10.7398 14.4488 10.6459 14.3549L4.64592 8.35489C4.59935 8.30845 4.56241 8.25327 4.5372 8.19253C4.512 8.13178 4.49902 8.06666 4.49902 8.00089C4.49902 7.93513 4.512 7.87001 4.5372 7.80926C4.56241 7.74852 4.59935 7.69334 4.64592 7.64689L10.6459 1.64689C10.6924 1.60033 10.7475 1.56339 10.8083 1.53818C10.869 1.51297 10.9341 1.5 10.9999 1.5C11.0657 1.5 11.1308 1.51297 11.1916 1.53818C11.2523 1.56339 11.3075 1.60033 11.3539 1.64689Z"
                                fill="#6B7280" fill-opacity="0.5" />
                        </svg>

                        <div class="text-2 ml-11" :class="{ disable_color: is_settings_mode }">Назад</div>
                    </div>

                    <div class="num-page-box num-page-txt a-c cntr-row j-c" :class="{ disable_color: is_settings_mode }">1
                    </div>

                    <div class="blue-box a-c cntr-row j-c text-white ml-10"
                        :class="{ disable_bg_color_num_page: is_settings_mode, disable_color_selected_page: is_settings_mode }">
                        2
                    </div>

                    <div class="num-page-box num-page-txt a-c cntr-row j-c" :class="{ disable_color: is_settings_mode }">3
                    </div>

                    <div class="num-page-box num-page-txt a-c cntr-row j-c" :class="{ disable_color: is_settings_mode }">4
                    </div>

                    <div class="num-page-box num-page-txt a-c cntr-row j-c" :class="{ disable_color: is_settings_mode }">...
                    </div>
                    <div class="num-page-box num-page-txt a-c cntr-row j-c" :class="{ disable_color: is_settings_mode }">100
                    </div>
                    <div class="grey-box w-98 h-40 cntr-row a-c ml-10 btn_onwards cur-pointer">

                        <div class="text-2 ml-16 " :class="{ disable_color: is_settings_mode }">Далее</div>

                        <svg v-show="!is_settings_mode" class="ml-11" width="8" height="14" viewBox="0 0 8 14" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M0.646039 0.646009C0.692485 0.599446 0.74766 0.562503 0.808405 0.537296C0.869151 0.51209 0.934272 0.499115 1.00004 0.499115C1.06581 0.499115 1.13093 0.51209 1.19167 0.537296C1.25242 0.562503 1.30759 0.599446 1.35404 0.646009L7.35404 6.64601C7.4006 6.69245 7.43754 6.74763 7.46275 6.80838C7.48796 6.86912 7.50093 6.93424 7.50093 7.00001C7.50093 7.06578 7.48796 7.1309 7.46275 7.19164C7.43754 7.25239 7.4006 7.30756 7.35404 7.35401L1.35404 13.354C1.26015 13.4479 1.13281 13.5006 1.00004 13.5006C0.867263 13.5006 0.739926 13.4479 0.646039 13.354C0.552152 13.2601 0.499407 13.1328 0.499407 13C0.499407 12.8672 0.552152 12.7399 0.646039 12.646L6.29304 7.00001L0.646039 1.35401C0.599476 1.30756 0.562533 1.25239 0.537326 1.19164C0.51212 1.1309 0.499146 1.06578 0.499146 1.00001C0.499146 0.934242 0.51212 0.86912 0.537326 0.808375C0.562533 0.74763 0.599476 0.692455 0.646039 0.646009Z"
                                fill="#6B7280" />
                        </svg>
                        <svg v-show="is_settings_mode" class="ml-11" width="16" height="16" viewBox="0 0 16 16" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M4.64592 1.64689C4.69236 1.60033 4.74754 1.56339 4.80828 1.53818C4.86903 1.51297 4.93415 1.5 4.99992 1.5C5.06568 1.5 5.13081 1.51297 5.19155 1.53818C5.2523 1.56339 5.30747 1.60033 5.35392 1.64689L11.3539 7.64689C11.4005 7.69334 11.4374 7.74852 11.4626 7.80926C11.4878 7.87001 11.5008 7.93513 11.5008 8.00089C11.5008 8.06666 11.4878 8.13178 11.4626 8.19253C11.4374 8.25327 11.4005 8.30845 11.3539 8.35489L5.35392 14.3549C5.26003 14.4488 5.13269 14.5015 4.99992 14.5015C4.86714 14.5015 4.7398 14.4488 4.64592 14.3549C4.55203 14.261 4.49929 14.1337 4.49929 14.0009C4.49929 13.8681 4.55203 13.7408 4.64592 13.6469L10.2929 8.00089L4.64592 2.35489C4.59935 2.30845 4.56241 2.25327 4.5372 2.19253C4.512 2.13178 4.49902 2.06666 4.49902 2.00089C4.49902 1.93513 4.512 1.87001 4.5372 1.80926C4.56241 1.74852 4.59935 1.69334 4.64592 1.64689Z"
                                fill="#6B7280" fill-opacity="0.5" />
                        </svg>

                    </div>
                </div>

                <div class="cntr-row a-c">
                    <div class="text-2" :class="{ disable_color: is_settings_mode }">Показать</div>
                    <div @click="show_selecter_page = !show_selecter_page"
                        class="btn_pagination grey-box w-113 h-40 cntr-row a-c j-b ml-11">
                        <div v-show="show_selecter_page" class="cntr_select_page"><select-page /></div>

                        <div class="text-3 ml-11" :class="{ disable_color: is_settings_mode }">10</div>

                        <svg v-show="!is_settings_mode" class="mr-16" width="12" height="8" viewBox="0 0 12 8" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M6.30969 6.93476C6.26905 6.9755 6.22077 7.00783 6.16762 7.02988C6.11446 7.05194 6.05748 7.06329 5.99994 7.06329C5.94239 7.06329 5.88541 7.05194 5.83226 7.02988C5.77911 7.00783 5.73083 6.9755 5.69019 6.93476L0.440187 1.68476C0.358037 1.60261 0.311884 1.49119 0.311884 1.37501C0.311884 1.25883 0.358037 1.14741 0.440187 1.06526C0.522337 0.98311 0.633758 0.936958 0.749938 0.936958C0.866116 0.936958 0.977537 0.98311 1.05969 1.06526L5.99994 6.00639L10.9402 1.06526C11.0223 0.983111 11.1338 0.936959 11.2499 0.936959C11.3661 0.936959 11.4775 0.983111 11.5597 1.06526C11.6418 1.14741 11.688 1.25883 11.688 1.37501C11.688 1.49119 11.6418 1.60261 11.5597 1.68476L6.30969 6.93476Z"
                                fill="#374151" />
                        </svg>
                        <svg v-show="is_settings_mode" class="mr-16" width="14" height="8" viewBox="0 0 14 8" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M0.645917 0.646894C0.692363 0.60033 0.747539 0.563387 0.808284 0.538181C0.869029 0.512974 0.93415 0.5 0.999917 0.5C1.06568 0.5 1.13081 0.512974 1.19155 0.538181C1.2523 0.563387 1.30747 0.60033 1.35392 0.646894L6.99992 6.29389L12.6459 0.646894C12.6924 0.600406 12.7476 0.563529 12.8083 0.53837C12.8691 0.513211 12.9342 0.500262 12.9999 0.500262C13.0657 0.500262 13.1308 0.513211 13.1915 0.53837C13.2522 0.563529 13.3074 0.600406 13.3539 0.646894C13.4004 0.693381 13.4373 0.748571 13.4624 0.80931C13.4876 0.870049 13.5005 0.93515 13.5005 1.00089C13.5005 1.06664 13.4876 1.13174 13.4624 1.19248C13.4373 1.25322 13.4004 1.30841 13.3539 1.35489L7.35392 7.35489C7.30747 7.40146 7.2523 7.4384 7.19155 7.46361C7.13081 7.48881 7.06568 7.50179 6.99992 7.50179C6.93415 7.50179 6.86903 7.48881 6.80828 7.46361C6.74754 7.4384 6.69236 7.40146 6.64592 7.35489L0.645917 1.35489C0.599354 1.30845 0.562411 1.25327 0.537205 1.19253C0.511998 1.13178 0.499023 1.06666 0.499023 1.00089C0.499023 0.935126 0.511998 0.870005 0.537205 0.80926C0.562411 0.748515 0.599354 0.693339 0.645917 0.646894Z"
                                fill="#6B7280" fill-opacity="0.5" />
                        </svg>


                    </div>
                </div>
            </div>

        </div>
    </div>
</template>



<script>

import PartLeftListDelivers from '../delivers/PartLeftListDelivers.vue'
import ModalIssave from './ModalIsSave.vue'
import SelecterIndex from '../SelecterIndex.vue'
import SelecterPage from '../elements/SelecterPage.vue'
import SelecterCPC from '../SelecterCPC.vue'

export default {
    name: 'SettingsLimits',
    data() {
        return {

            is_check: true,
            show_modal_is_save: false,
            show_selecter: false,
            show_selecter_index: false,
            show_selecter_page: false,
            is_sorted_active_deliver: false,
            is_sorted_index: false,
            is_selected_index: false,
            is_settings_mode: false,
            show_selecter_cpc: false,
        }
    },
    components: {
        'part-left': PartLeftListDelivers,
        'modal-issave': ModalIssave,
        'select-index': SelecterIndex,
        'select-page': SelecterPage,
        'select-cpc': SelecterCPC
    }
}

// function handle_click_save() {
//     show_modal_is_save = true
//     is_settings_mode = false
// }

</script>

<style scoped>
.cntr_selecter_cpc {
    position: absolute;
    top: 10px;
    left: 50%;
}
.td_chevron {
    position: absolute;
    top: 50%;
    transform: translateY(-30%);
    right: 14.5px;
}
.text-3 {
    color: var(--gray-500, #6B7280);

    /* Input/Default Medium */
    font-family: Inter;
    font-size: 15px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    letter-spacing: 0.075px;
}

.cntr_select_page {
    position: absolute;
    bottom: 250px;
    left: -30px;
}

.btn_pagination {
    position: relative;
    cursor: pointer;
}

.btn_pagination:hover {
    background: var(--d-9-d-9-d-9, #F3F4F6);
    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);
}

.td_input {
    width: 90%;
    outline: none;
    border: none;
    color: var(--d-9-d-9-d-9, #374151);

    /* Input/Default Medium */
    font-family: Inter;
    font-size: 15px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    letter-spacing: 0.075px;
}

/* .td_input:focus td {
    background: var(--d-9-d-9-d-9, #F3F4F6);
} */

td:has(input:focus) {
    background: var(--d-9-d-9-d-9, #F3F4F6);
}

input:focus {
    background: var(--d-9-d-9-d-9, #F3F4F6);
}

.limits_menu_save {
    position: absolute;
    top: 0;
    left: 60vw;
    border-radius: 5.224px;
    border: 0.871px solid var(--gray-200, #E5E7EB);
    display: flex;
    align-items: center;
    padding-left: 18px;
    padding-right: 17px;
    cursor: pointer;
}

.disable_bg_color_num_page {
    background: rgba(59, 130, 246, 0.50) !important;
}

.disable_color_selected_page {
    color: rgba(255, 255, 255, 0.50) !important;
}

.index_header:hover {
    background: var(--d-9-d-9-d-9, #F3F4F6) !important;
}

.menu_settings {
    width: 8vw;
    padding-left: 16px;
    margin-left: 60vw;
}

.menu_settings:hover {
    background: var(--d-9-d-9-d-9, #F3F4F6);
}

.arrow_sort {
    position: absolute;
    top: 50%;
    transform: translateY(-40%);
    right: 80px;
}

.color2 {
    color: #3B82F6 !important;
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
    margin-top: 10vh;
}

.cntr-table {
    margin-top: 21px;
    padding-right: 27px;
    overflow: scroll;
    width: 75vw;
    height: 60vh;
    position: relative;
}


/* TABLES */

td,
th {
    border: 1px solid var(--gray-200, #E5E7EB);
    position: relative;
    height: 44px;
    width: 100px;
}

td {
    text-align: left;
    padding-left: 20px;
}

.header1 {
    position: sticky;
    top: 0px;
    background-color: #fff;
    z-index: 11;
    border: 1px solid var(--gray-200, #E5E7EB);
}

tr:first-child th:first-child {
    position: sticky;
    left: 0;
    background-color: #fff;
    z-index: 11;
}

tr:first-child th:nth-child(2) {
    position: sticky;
    left: 210px;
    background-color: #fff;
    z-index: 11;

}

tr:first-child th {
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
    text-align: left;
    padding-left: 20px;
}

tr:nth-child(n + 2) th {
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

/* fixing left first and second column */
tr:nth-child(3n - 1) th:first-child {
    position: sticky;
    left: 0;
    width: 110px;
    background-color: #fff;
    z-index: 10;
    text-align: left;
    padding-left: 20px;
}

tr:nth-child(3n - 1) th:nth-child(2) {
    position: sticky;
    left: 210px;
    width: 110px;
    background-color: #fff;
    z-index: 10;
    text-align: left;
    padding-left: 20px;
}

tr:nth-child(3n) th:first-child {
    position: sticky;
    left: 210px;
    width: 110px;
    background-color: #fff;
    z-index: 10;
    text-align: left;
    padding-left: 20px;
}

tr:nth-child(3n + 4) th:first-child {
    position: sticky;
    left: 210px;
    width: 110px;
    background-color: #fff;
    z-index: 10;
    text-align: left;
    padding-left: 20px;
}


table {
    margin-top: 18px;
    border-collapse: collapse;
    width: 1600px;
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

.disable_color {
    color: rgba(107, 114, 128, 0.50) !important;
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