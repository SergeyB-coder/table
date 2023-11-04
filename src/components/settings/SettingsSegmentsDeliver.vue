<template>
    <modal-filters v-show="show_modal_filters" :show_modal_filters="show_modal_filters" />
    <div class="cntr-row">
        <part-left />



        <div class="cntr-bg-2">
            <div @click="show_modal_filters = false" v-show="show_modal_filters" class="pseudo_bg"></div>


            <div class="text-1">Настройка сегментов доставок</div>
            <div class="cntr-row sub_menu_ssd">
                <label class="text__sub_menu_ssd">Настройка сегментов доставок</label>
                <label class="text__sub_menu_ssd_dis ml-26">Сегменты</label>
                <label class="text__sub_menu_ssd_dis ml-26">Интересы ВК, ВКР и МТ</label>
            </div>
            <div class="line">
            </div>


            <!-- MENU -->
            <div class="cntr-row mt-18 pos-rel">
                <div class="grey-box cntr-row a-c menu_filters pos-rel cur-pointer h-40"
                    @click="show_modal_filters = true">
                    <svg width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path
                            d="M12.8333 4.22925H9.33331C9.09415 4.22925 8.89581 4.03091 8.89581 3.79175C8.89581 3.55258 9.09415 3.35425 9.33331 3.35425H12.8333C13.0725 3.35425 13.2708 3.55258 13.2708 3.79175C13.2708 4.03091 13.0725 4.22925 12.8333 4.22925Z"
                            fill="#6B7280" />
                        <path
                            d="M3.50002 4.22925H1.16669C0.92752 4.22925 0.729187 4.03091 0.729187 3.79175C0.729187 3.55258 0.92752 3.35425 1.16669 3.35425H3.50002C3.73919 3.35425 3.93752 3.55258 3.93752 3.79175C3.93752 4.03091 3.73919 4.22925 3.50002 4.22925Z"
                            fill="#6B7280" />
                        <path
                            d="M5.83335 6.27083C4.46835 6.27083 3.35419 5.15667 3.35419 3.79167C3.35419 2.42667 4.46835 1.3125 5.83335 1.3125C7.19835 1.3125 8.31252 2.42667 8.31252 3.79167C8.31252 5.15667 7.19835 6.27083 5.83335 6.27083ZM5.83335 2.1875C4.94669 2.1875 4.22919 2.905 4.22919 3.79167C4.22919 4.67833 4.94669 5.39583 5.83335 5.39583C6.72002 5.39583 7.43752 4.67833 7.43752 3.79167C7.43752 2.905 6.72002 2.1875 5.83335 2.1875Z"
                            fill="#6B7280" />
                        <path
                            d="M12.8333 10.6458H10.5C10.2608 10.6458 10.0625 10.4474 10.0625 10.2083C10.0625 9.96909 10.2608 9.77075 10.5 9.77075H12.8333C13.0725 9.77075 13.2708 9.96909 13.2708 10.2083C13.2708 10.4474 13.0725 10.6458 12.8333 10.6458Z"
                            fill="#6B7280" />
                        <path
                            d="M4.66669 10.6458H1.16669C0.92752 10.6458 0.729187 10.4474 0.729187 10.2083C0.729187 9.96909 0.92752 9.77075 1.16669 9.77075H4.66669C4.90585 9.77075 5.10419 9.96909 5.10419 10.2083C5.10419 10.4474 4.90585 10.6458 4.66669 10.6458Z"
                            fill="#6B7280" />
                        <path
                            d="M8.16667 12.6876C6.80167 12.6876 5.6875 11.5734 5.6875 10.2084C5.6875 8.84341 6.80167 7.72925 8.16667 7.72925C9.53167 7.72925 10.6458 8.84341 10.6458 10.2084C10.6458 11.5734 9.53167 12.6876 8.16667 12.6876ZM8.16667 8.60425C7.28 8.60425 6.5625 9.32175 6.5625 10.2084C6.5625 11.0951 7.28 11.8126 8.16667 11.8126C9.05333 11.8126 9.77083 11.0951 9.77083 10.2084C9.77083 9.32175 9.05333 8.60425 8.16667 8.60425Z"
                            fill="#6B7280" />
                    </svg>



                    <div @click="show_modal = !show_modal" class=" text-2 ml-11 cur-pointer">Все фильтры</div>
                </div>
            </div>

            <!-- TABLE -->
            <div class="cntr-table">
                <table class="scroll_table">
                    <tr class="header1 ">
                        <th @click="sort_id=sort_id+1" :class="{ selected_color: sort_states[sort_id%3] !== 0 }">
                            ID
                            <svg 
                                class="id_svg" 
                                v-show="sort_states[sort_id % 3] !== 0" 
                                :class="{rotate_180: sort_states[sort_id % 3] === 2}"
                                width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M8.00002 12C8.13263 12 8.25981 11.9473 8.35358 11.8535C8.44734 11.7598 8.50002 11.6326 8.50002 11.5V5.70698L10.646 7.85398C10.6925 7.90047 10.7477 7.93734 10.8084 7.9625C10.8692 7.98766 10.9343 8.00061 11 8.00061C11.0658 8.00061 11.1309 7.98766 11.1916 7.9625C11.2523 7.93734 11.3075 7.90047 11.354 7.85398C11.4005 7.80749 11.4374 7.7523 11.4625 7.69156C11.4877 7.63082 11.5007 7.56572 11.5007 7.49998C11.5007 7.43423 11.4877 7.36913 11.4625 7.30839C11.4374 7.24766 11.4005 7.19247 11.354 7.14598L8.35402 4.14598C8.30758 4.09941 8.2524 4.06247 8.19165 4.03727C8.13091 4.01206 8.06579 3.99908 8.00002 3.99908C7.93425 3.99908 7.86913 4.01206 7.80839 4.03727C7.74764 4.06247 7.69247 4.09941 7.64602 4.14598L4.64602 7.14598C4.55213 7.23986 4.49939 7.3672 4.49939 7.49998C4.49939 7.63275 4.55213 7.76009 4.64602 7.85398C4.73991 7.94787 4.86725 8.00061 5.00002 8.00061C5.1328 8.00061 5.26013 7.94787 5.35402 7.85398L7.50002 5.70698L7.50002 11.5C7.50002 11.6326 7.5527 11.7598 7.64647 11.8535C7.74024 11.9473 7.86741 12 8.00002 12Z"
                                    fill="#006AFF" />
                            </svg>

                        </th>
                        <th @click="sort_segment_ind=sort_segment_ind+1" :class="{ selected_color: sort_states[sort_segment_ind % 3] !== 0 }">
                            Сегмент
                            <svg 
                                class="segment_svg" 
                                v-show="sort_states[sort_segment_ind % 3] !== 0" 
                                :class="{rotate_180: sort_states[sort_segment_ind % 3] === 2}"
                                width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M8.00002 12C8.13263 12 8.25981 11.9473 8.35358 11.8535C8.44734 11.7598 8.50002 11.6326 8.50002 11.5V5.70698L10.646 7.85398C10.6925 7.90047 10.7477 7.93734 10.8084 7.9625C10.8692 7.98766 10.9343 8.00061 11 8.00061C11.0658 8.00061 11.1309 7.98766 11.1916 7.9625C11.2523 7.93734 11.3075 7.90047 11.354 7.85398C11.4005 7.80749 11.4374 7.7523 11.4625 7.69156C11.4877 7.63082 11.5007 7.56572 11.5007 7.49998C11.5007 7.43423 11.4877 7.36913 11.4625 7.30839C11.4374 7.24766 11.4005 7.19247 11.354 7.14598L8.35402 4.14598C8.30758 4.09941 8.2524 4.06247 8.19165 4.03727C8.13091 4.01206 8.06579 3.99908 8.00002 3.99908C7.93425 3.99908 7.86913 4.01206 7.80839 4.03727C7.74764 4.06247 7.69247 4.09941 7.64602 4.14598L4.64602 7.14598C4.55213 7.23986 4.49939 7.3672 4.49939 7.49998C4.49939 7.63275 4.55213 7.76009 4.64602 7.85398C4.73991 7.94787 4.86725 8.00061 5.00002 8.00061C5.1328 8.00061 5.26013 7.94787 5.35402 7.85398L7.50002 5.70698L7.50002 11.5C7.50002 11.6326 7.5527 11.7598 7.64647 11.8535C7.74024 11.9473 7.86741 12 8.00002 12Z"
                                    fill="#006AFF" />
                            </svg>
                        </th>
                        <th>ГЕО</th>
                        <th>Исключенное ГЕО</th>
                        <th>Возраст</th>
                        <th>Интересы</th>
                    </tr>
                    <tr v-show="create_new_deliver" class="new_deliver">
                        <td>Новая доставка</td>
                        <td>-</td>
                        <td>-</td>
                        <td>-</td>
                        <td>-</td>
                        <td>-</td>
                    </tr>
                    <tr>
                        <td>вапа</td>
                        <td>
                            1. Россия 18+<br />
                            2. Широкая аудитория Россия 18+
                        </td>
                        <td>Россия</td>
                        <td>-</td>
                        <td>От 18</td>
                        <td>-</td>
                    </tr>
                    <tr>
                        <td>дад</td>
                        <td>Кастомный сегмент</td>
                        <td>Краснодарский край</td>
                        <td>-</td>
                        <td>От 18 до 50</td>
                        <td>-</td>
                    </tr>
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
// import ModalIssave from './ModalIsSave.vue'
// import SelecterIndex from '../SelecterIndex.vue'
import SelecterPage from '../SelecterPage.vue'
// import SelecterCPC from '../SelecterCPC.vue'
import ModalFilters from './ModalIFilters.vue'

export default {
    name: 'SettingsLimits',
    data() {
        return {

            is_check: true,
            show_modal_filters: false,
            show_selecter: false,
            show_selecter_index: false,
            show_selecter_page: false,
            is_sorted_active_deliver: false,
            is_sorted_index: false,
            is_selected_index: false,
            is_settings_mode: false,
            show_selecter_cpc: false,
            sort_id: false,
            sort_states: [0, 1, 2],
            sort_segment_ind: 0,
            create_new_deliver: false
        }
    },
    components: {
        'part-left': PartLeftListDelivers,
        // 'modal-issave': ModalIssave,
        'modal-filters': ModalFilters,
        // 'select-index': SelecterIndex,
        'select-page': SelecterPage,
    }
}

</script>

<style scoped>
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

.menu_filters {
    padding: 0 16px;
    margin-left: calc(100% - 140px)
}

.menu_filters:hover {
    background-color: #F2F7FF
}

.id_svg {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    left: 20%;
}

.segment_svg {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    left: 40%;
}

.selected_color {
    color: #3B82F6 !important
}
.sub_menu_ssd {
    margin-top: 31px;
}

.ml-26 {
    margin-left: 26px;
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

.text__sub_menu_ssd {
    color: #000;
    font-family: Inter;
    font-size: 15px;
    font-style: normal;
    font-weight: 600;
    line-height: normal;
    letter-spacing: 0.075px;
    padding-bottom: 5px;
    border-bottom: solid 2px #6B7280;
}

.text__sub_menu_ssd_dis {
    color: var(--d-9-d-9-d-9, #6B7280);
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
    right: 0px;
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

td:has(input:focus) {
    background: var(--d-9-d-9-d-9, #F3F4F6);
}

input:focus {
    background: var(--d-9-d-9-d-9, #F3F4F6);
}


.disable_bg_color_num_page {
    background: rgba(59, 130, 246, 0.50) !important;
}

.disable_color_selected_page {
    color: rgba(255, 255, 255, 0.50) !important;
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

.mt-168 {
    margin-top: 6vh;
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

th {
    cursor: pointer
}

th:hover {
    background-color: #F3F4F6;
}

.header1 {
    position: sticky;
    top: 0px;
    background-color: #fff;
    z-index: 11;
    border: 1px solid var(--gray-200, #E5E7EB);
}



.new_deliver td {
    color: #F87171;
    border: 1px solid  #F87171 !important;
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

td {
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




table {
    margin-top: 18px;
    /* border-collapse: collapse; */
    border-spacing:0;
    width: 1400px;
}


.rotate_180 {
    transform: rotate(180deg) translateY(50%);
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
    cursor: pointer;
}

.num-page-box:hover {
    background-color: #F3F4F6;
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
    margin-top: -1px;
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
}
</style>