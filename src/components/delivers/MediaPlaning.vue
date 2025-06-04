<template>
    <modal-isadd-user :text="'Новый пользователь добавлен'" v-show="show_modal_is_save" />
    <modal-isadd-user :text="'Удаление пользователя подтверждено'" v-show="show_modal_is_del" />
    <modal-filters-users v-show="show_modal_filters" :show_modal_filters="show_modal_filters" />

    <modal-filters-reports v-show="show_report_filters" :show_segments_list_id="show_segments_list_id"
        @toggle-segments-list="toggleSegmentsList" />

    <modal-delete v-show="show_modal_delete" />
    <ModalIsSave v-show="show_modal_is_save" />
    <ModalWarning v-show="false" />
    <modal-list-delivers v-show="show_modal_list_delivers" :text="text_list_delivers" />
    <modal-list-delivers v-show="show_segments_list_id" :text="text_list_id" />

    <div class="cntr-row">
        <part-left />
        <div class="cntr-bg-2">
            <div @click="() => { show_segments_list_id = false; show_modal_filters = false; show_modal_list_delivers = false; show_modal_is_del = false; show_report_filters = false }"
                v-show="show_modal_filters || show_modal_is_save || show_modal_is_del || show_modal_list_delivers || show_report_filters"
                class="pseudo_bg"></div>


            <div class="text-1">{{
                mode === "settings" ? 'Настройки медиаплана' :
                    addexport_mode ? 'Добавить экспорт' : 'Медиапланирование' }}</div>

            <div class="cntr-row sub_menu_ssd g-26"
                v-show="create_plane_mode || finance_mode || mode === 'create' || mode === 'finance' || mode === 'show_plane'">
                <label class=""
                    :class="{ text__sub_menu_ssd_dis: selected !== 'general', text__sub_menu_ssd: selected === 'general' }"
                    @click="() => {
                        mode = 'create'
                        selectMenuItem('general');
                        create_plane_mode = true;
                        show_plane_mode = false;
                        finance_mode = false;
                    }">
                    Создание медиаплана
                </label>
                <label class=" ml-26"
                    :class="{ 'text__sub_menu_ssd_dis': selected !== 'functionality', text__sub_menu_ssd: selected === 'functionality' }"
                    @click="() => {
                        selectMenuItem('functionality');
                        show_plane_mode = false;
                        finance_mode = true;
                        mode = 'finance'
                        create_plane_mode = false;
                    }">
                    Распределение бюджета
                </label>
                <label class=" ml-26"
                    :class="{ 'text__sub_menu_ssd_dis': selected !== 'content', text__sub_menu_ssd: selected === 'content' }"
                    @click="() => {
                        selectMenuItem('content');
                        mode = 'show_plane'
                        show_plane_mode = true;
                        create_plane_mode = false;
                        finance_mode = false
                    }">
                    Просмотр медиаплана
                </label>
                <label class=" ml-26"
                    :class="{ 'text__sub_menu_ssd_dis': selected !== 'results', text__sub_menu_ssd: selected === 'results' }"
                    @click="() => {
                        selectMenuItem('results');
                        show_plane_mode = true;
                        create_plane_mode = false;
                        finance_mode = false
                        is_results = true
                    }">
                    Результаты
                </label>
            </div>

            <div class="line" style="margin-top: 6px;">
            </div>


            <!-- MENU -->
            <div style="width: 100%; gap: 0" class="segment_menu mt-18 pos-rel">
                <modal_new_interest v-show="show_modal_new_interest" />

                <!-- cancel bnt -->
                <div style="width: 100%; display: flex; gap: 8px; justify-content: end;"
                    v-show="mode === 'settings' || mode === 'show_plane'">
                    <div @click="show_modal_is_save = true" v-show="mode === 'settings' || is_results"
                        class="grey-box cntr-row a-c menu_filters pos-rel cur-pointer h-40">
                        <SvgSave />
                        <div class="text-2 ml-11">Сохранить</div>
                    </div>
                    <div @click="mode = 'main'" class="grey-box cntr-row a-c menu_filters pos-rel cur-pointer h-40">
                        <SvgCancelGrey />
                        <div class="text-2 ml-11">Отмена</div>
                    </div>
                </div>

                <div class="report_menu" v-show="is_settings_mode || report_mode || mode === 'create'">
                    <div @click="show_selecter_datetime = !show_selecter_datetime" v-show="mode === 'create'"
                        class="grey-box cntr-row a-c menu_filters pos-rel cur-pointer h-40">
                        <SvgCalendar v-show="!show_selecter_datetime"/>
                        <SvgCalendarBlue v-show="show_selecter_datetime"/>
                        <div class="text-2 ml-11">Период</div>
                        <SelecterDateTime v-show="show_selecter_datetime" />
                    </div>
                    <div class="grey-box cntr-row a-c menu_filters pos-rel cur-pointer h-40">
                        <SvgEdit />
                        <div @click="show_input_name_plane = !show_input_name_plane" class="text-2 ml-11">Наименование
                            медиаплана</div>
                        <InputMediaplane v-show="show_input_name_plane" />
                    </div>
                    <div @click="show_input_reserve = !show_input_reserve"
                        class="grey-box cntr-row a-c menu_filters pos-rel cur-pointer h-40">
                        <SvgReserve />
                        <div class="text-2 ml-11">Резерв</div>
                        <InputMediaplane v-show="show_input_reserve" />
                    </div>
                    <div @click="is_consider_click = !is_consider_click"
                        class="grey-box cntr-row a-c menu_filters pos-rel cur-pointer h-40"
                        :class="{border_blue: is_consider_click}"
                    >
                        <SvgSquare v-show="!is_consider_click" />
                        <SvgSquareCheck v-show="is_consider_click" />
                        <div class="text-2 ml-11">Учитывать клики</div>
                    </div>
                </div>


                <div style="width: 100%;" class="segment_menu" v-show="mode === 'main'">

                    <div class="grey-box cntr-row a-c menu_filters pos-rel cur-pointer h-40"
                        @click="error_export = !is_check; show_export_success = !show_export_success"
                        v-show="!config_mode">
                        <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M8.00356 5.59738C7.80103 5.3972 7.47456 5.39911 7.27438 5.60165L5.64305 7.2522L4.33655 6.0133C4.12991 5.81735 3.80356 5.82602 3.60761 6.03265C3.41167 6.23929 3.42033 6.56564 3.62697 6.76159L4.91798 7.98581L3.56064 9.35914C3.36046 9.56168 3.36237 9.88815 3.56491 10.0883C3.76744 10.2885 4.09391 10.2866 4.29409 10.0841L5.66643 8.69554L7.55211 10.4837C7.75875 10.6796 8.0851 10.671 8.28105 10.4643C8.477 10.2577 8.46833 9.93133 8.26169 9.73538L6.3915 7.96194L8.00783 6.32656C8.20801 6.12402 8.2061 5.79756 8.00356 5.59738Z"
                                fill="#6B7280" />
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M3.32076 1.80815C4.27493 1.50652 6.6449 0.888 8.40442 0.888C9.3641 0.888 10.0442 1.18716 10.478 1.65031C10.5781 1.75723 10.6619 1.86955 10.7313 1.98397H11.0843C13.2934 1.98397 15.0843 3.77483 15.0843 5.98397V10.0335C15.0843 12.2427 13.2934 14.0335 11.0843 14.0335H10.3304C10.1876 14.2469 10.0202 14.4279 9.83458 14.5785C9.25936 15.045 8.5796 15.1606 8.10973 15.1228L8.09759 15.1218L8.0855 15.1203C7.23944 15.0171 5.11614 14.7209 3.37843 14.3591C2.82992 14.2449 2.35404 14.1032 1.98577 13.8436C1.58254 13.5594 1.36476 13.1771 1.24436 12.714C1.13222 12.2827 1.09605 11.7459 1.06779 11.1139C1.05995 10.9386 1.05269 10.7534 1.04497 10.5566C1.02398 10.0212 0.999615 9.39984 0.951091 8.65863L0.949829 8.63935V4.38004C0.949829 3.49041 1.27815 2.88304 1.80761 2.47765C2.24192 2.14512 2.79011 1.97396 3.21158 1.84238L3.32076 1.80815ZM10.9659 5.33913C10.9816 4.57696 10.9965 3.87925 11.0088 3.3173H11.0843C12.557 3.3173 13.7509 4.51121 13.7509 5.98397V10.0335C13.7509 11.5063 12.557 12.7002 11.0843 12.7002H10.8095C10.8348 12.5155 10.8488 12.3194 10.8504 12.1116C10.8535 11.7204 10.8596 11.2302 10.8678 10.6777H12.1429C12.4349 10.6777 12.6716 10.441 12.6716 10.149C12.6716 9.85704 12.4349 9.62035 12.1429 9.62035H10.8846C10.8905 9.27004 10.8969 8.90667 10.9036 8.53705H12.1429C12.4349 8.53705 12.6716 8.30036 12.6716 8.00839C12.6716 7.71641 12.4349 7.47972 12.1429 7.47972H10.9233C10.9303 7.11639 10.9374 6.75324 10.9445 6.39646H12.1429C12.4349 6.39646 12.6716 6.15977 12.6716 5.8678C12.6716 5.57583 12.4349 5.33913 12.1429 5.33913H10.9659ZM8.40442 2.06998C6.83315 2.06998 4.60538 2.64169 3.67704 2.93516L3.62351 2.95207L3.62351 2.95207L3.6235 2.95207C3.14196 3.10414 2.7874 3.21611 2.52617 3.41613C2.31189 3.58019 2.13181 3.82824 2.13181 4.38004V8.60075C2.1806 9.35046 2.20565 9.98931 2.22658 10.5233L2.22658 10.5233C2.23415 10.7162 2.24117 10.8953 2.24858 11.0611C2.27761 11.7101 2.31232 12.1243 2.3883 12.4166C2.45604 12.6771 2.54365 12.7908 2.66671 12.8775C2.82475 12.9889 3.09608 13.093 3.61936 13.202C5.30224 13.5524 7.37576 13.8426 8.21508 13.9454C8.43986 13.9607 8.79635 13.8987 9.09003 13.6605C9.36562 13.437 9.66137 12.997 9.66848 12.1022C9.68501 10.0218 9.78543 5.16541 9.8335 3.00009L9.83362 2.99474L9.83384 2.9894C9.83854 2.87271 9.79404 2.64915 9.61531 2.45833C9.45037 2.28223 9.11015 2.06998 8.40442 2.06998Z"
                                fill="#6B7280" />
                        </svg>

                        <div class=" text-2 ml-11 cur-pointer">Выгрузить медиаплан</div>
                    </div>
                    <div class="grey-box cntr-row a-c menu_filters pos-rel cur-pointer h-40" @click="mode = 'settings'"
                        v-show="!config_mode">
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
                        <div @click="show_modal = !show_modal" class=" text-2 ml-11 cur-pointer">Настройки медиаплана
                        </div>
                    </div>
                    <div class="grey-box cntr-row a-c menu_filters pos-rel cur-pointer h-40"
                        @click="show_modal_filters = true" v-show="!config_mode">

                        <svg-cancel-grey />
                        <div @click="show_modal = !show_modal" class=" text-2 ml-11 cur-pointer">Удалить медиаплан</div>
                    </div>
                    <!-- configure bnt -->
                    <div @click="() => { mode = 'show_plane'; }" v-show="!config_mode"
                        class="grey-box cntr-row a-c menu_filters pos-rel cur-pointer h-40">
                        <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path
                                d="M7.99995 10.8955C6.40661 10.8955 5.11328 9.60213 5.11328 8.0088C5.11328 6.41546 6.40661 5.12213 7.99995 5.12213C9.59328 5.12213 10.8866 6.41546 10.8866 8.0088C10.8866 9.60213 9.59328 10.8955 7.99995 10.8955ZM7.99995 6.12213C6.95995 6.12213 6.11328 6.9688 6.11328 8.0088C6.11328 9.0488 6.95995 9.89546 7.99995 9.89546C9.03995 9.89546 9.88661 9.0488 9.88661 8.0088C9.88661 6.9688 9.03995 6.12213 7.99995 6.12213Z"
                                fill="#6B7280" />
                            <path
                                d="M7.99997 14.0222C5.4933 14.0222 3.12664 12.5555 1.49997 10.0088C0.793304 8.90882 0.793304 7.11548 1.49997 6.00882C3.1333 3.46215 5.49997 1.99548 7.99997 1.99548C10.5 1.99548 12.8666 3.46215 14.4933 6.00882C15.2 7.10882 15.2 8.90215 14.4933 10.0088C12.8666 12.5555 10.5 14.0222 7.99997 14.0222ZM7.99997 2.99548C5.84664 2.99548 3.78664 4.28882 2.34664 6.54882C1.84664 7.32882 1.84664 8.68882 2.34664 9.46882C3.78664 11.7288 5.84664 13.0222 7.99997 13.0222C10.1533 13.0222 12.2133 11.7288 13.6533 9.46882C14.1533 8.68882 14.1533 7.32882 13.6533 6.54882C12.2133 4.28882 10.1533 2.99548 7.99997 2.99548Z"
                                fill="#6B7280" />
                        </svg>


                        <div class=" text-2 ml-11 cur-pointer">Посмотреть медиаплан</div>
                    </div>

                    <div @click="() => { mode = 'create'; }" v-show="!config_mode && !(mode === ' create')"
                        class="grey-box cntr-row a-c menu_filters pos-rel cur-pointer h-40">
                        <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path
                                d="M8.00004 15.1754C4.04671 15.1754 0.833374 11.9621 0.833374 8.00877C0.833374 4.05544 4.04671 0.842102 8.00004 0.842102C11.9534 0.842102 15.1667 4.05544 15.1667 8.00877C15.1667 11.9621 11.9534 15.1754 8.00004 15.1754ZM8.00004 1.8421C4.60004 1.8421 1.83337 4.60877 1.83337 8.00877C1.83337 11.4088 4.60004 14.1754 8.00004 14.1754C11.4 14.1754 14.1667 11.4088 14.1667 8.00877C14.1667 4.60877 11.4 1.8421 8.00004 1.8421Z"
                                fill="#6B7280" />
                            <path
                                d="M10.6667 8.50879H5.33337C5.06004 8.50879 4.83337 8.28212 4.83337 8.00879C4.83337 7.73546 5.06004 7.50879 5.33337 7.50879H10.6667C10.94 7.50879 11.1667 7.73546 11.1667 8.00879C11.1667 8.28212 10.94 8.50879 10.6667 8.50879Z"
                                fill="#6B7280" />
                            <path
                                d="M8 11.1754C7.72667 11.1754 7.5 10.9488 7.5 10.6754V5.3421C7.5 5.06877 7.72667 4.8421 8 4.8421C8.27333 4.8421 8.5 5.06877 8.5 5.3421V10.6754C8.5 10.9488 8.27333 11.1754 8 11.1754Z"
                                fill="#6B7280" />
                        </svg>
                        <div class=" text-2 ml-11 cur-pointer">Создать медиаплан</div>
                    </div>

                </div>
            </div>

            <!-- BODY -->
            <div class="cntr-table" :class="{ h_75: new_user }">
                <table class="scroll_table" v-show="!new_user && mode === 'main'">
                    <tr class="header1 ">
                        <th v-show="config_mode || true" style="width: 60px !important;"></th>
                        <th @click="sort_segment_ind = sort_segment_ind + 1"
                            :class="{ selected_color: sort_states[sort_segment_ind % 3] !== 0 }">
                            Медиаплан
                            <svg class="h_svg_mediaplane" v-show="sort_states[sort_segment_ind % 3] !== 0"
                                :class="{ rotate_180: sort_states[sort_segment_ind % 3] === 2 }" width="16" height="16"
                                viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M8.00002 12C8.13263 12 8.25981 11.9473 8.35358 11.8535C8.44734 11.7598 8.50002 11.6326 8.50002 11.5V5.70698L10.646 7.85398C10.6925 7.90047 10.7477 7.93734 10.8084 7.9625C10.8692 7.98766 10.9343 8.00061 11 8.00061C11.0658 8.00061 11.1309 7.98766 11.1916 7.9625C11.2523 7.93734 11.3075 7.90047 11.354 7.85398C11.4005 7.80749 11.4374 7.7523 11.4625 7.69156C11.4877 7.63082 11.5007 7.56572 11.5007 7.49998C11.5007 7.43423 11.4877 7.36913 11.4625 7.30839C11.4374 7.24766 11.4005 7.19247 11.354 7.14598L8.35402 4.14598C8.30758 4.09941 8.2524 4.06247 8.19165 4.03727C8.13091 4.01206 8.06579 3.99908 8.00002 3.99908C7.93425 3.99908 7.86913 4.01206 7.80839 4.03727C7.74764 4.06247 7.69247 4.09941 7.64602 4.14598L4.64602 7.14598C4.55213 7.23986 4.49939 7.3672 4.49939 7.49998C4.49939 7.63275 4.55213 7.76009 4.64602 7.85398C4.73991 7.94787 4.86725 8.00061 5.00002 8.00061C5.1328 8.00061 5.26013 7.94787 5.35402 7.85398L7.50002 5.70698L7.50002 11.5C7.50002 11.6326 7.5527 11.7598 7.64647 11.8535C7.74024 11.9473 7.86741 12 8.00002 12Z"
                                    fill="#006AFF" />
                            </svg>
                        </th>

                        <th class="" @click="sort_period_ind = sort_period_ind + 1"
                            :class="{ selected_color: sort_states[sort_period_ind % 3] !== 0 }">
                            Период
                            <svg style="left: 40% !important" class="h_svg_mediaplane"
                                v-show="sort_states[sort_period_ind % 3] !== 0"
                                :class="{ rotate_180: sort_states[sort_period_ind % 3] === 2 }" width="16" height="16"
                                viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M8.00002 12C8.13263 12 8.25981 11.9473 8.35358 11.8535C8.44734 11.7598 8.50002 11.6326 8.50002 11.5V5.70698L10.646 7.85398C10.6925 7.90047 10.7477 7.93734 10.8084 7.9625C10.8692 7.98766 10.9343 8.00061 11 8.00061C11.0658 8.00061 11.1309 7.98766 11.1916 7.9625C11.2523 7.93734 11.3075 7.90047 11.354 7.85398C11.4005 7.80749 11.4374 7.7523 11.4625 7.69156C11.4877 7.63082 11.5007 7.56572 11.5007 7.49998C11.5007 7.43423 11.4877 7.36913 11.4625 7.30839C11.4374 7.24766 11.4005 7.19247 11.354 7.14598L8.35402 4.14598C8.30758 4.09941 8.2524 4.06247 8.19165 4.03727C8.13091 4.01206 8.06579 3.99908 8.00002 3.99908C7.93425 3.99908 7.86913 4.01206 7.80839 4.03727C7.74764 4.06247 7.69247 4.09941 7.64602 4.14598L4.64602 7.14598C4.55213 7.23986 4.49939 7.3672 4.49939 7.49998C4.49939 7.63275 4.55213 7.76009 4.64602 7.85398C4.73991 7.94787 4.86725 8.00061 5.00002 8.00061C5.1328 8.00061 5.26013 7.94787 5.35402 7.85398L7.50002 5.70698L7.50002 11.5C7.50002 11.6326 7.5527 11.7598 7.64647 11.8535C7.74024 11.9473 7.86741 12 8.00002 12Z"
                                    fill="#006AFF" />
                            </svg>
                        </th>
                        <th>Дата создания</th>
                        <th>Статус</th>
                    </tr>
                    <tr v-for="segment in segments" v-bind:key="segment.id">
                        <td @click="is_check = !is_check" v-show="config_mode || true"
                            :class="{ border_red: error_export }">
                            <svg-fidcheck :is_check="is_check" :error_export="error_export" />
                            <svg class="svg_check" v-show="is_check" width="10" height="8" viewBox="0 0 10 8"
                                :class="{ brd_red: error_export }" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path
                                    d="M3.5775 7.1675C3.3775 7.1675 3.1875 7.0875 3.0475 6.9475L0.2175 4.1175C-0.0725 3.8275 -0.0725 3.3475 0.2175 3.0575C0.5075 2.7675 0.9875 2.7675 1.2775 3.0575L3.5775 5.3575L8.7175 0.2175C9.0075 -0.0725 9.4875 -0.0725 9.7775 0.2175C10.0675 0.5075 10.0675 0.987499 9.7775 1.2775L4.1075 6.9475C3.9675 7.0875 3.7775 7.1675 3.5775 7.1675Z"
                                    :fill="is_check ? '#3B82F6' : '#6B7280'" />
                            </svg>
                        </td>
                        <td>
                            <label>{{ segment.plane }}</label>
                        </td>
                        <td>
                            <label>{{ segment.period }}</label>
                        </td>
                        <td>
                            <label>{{ segment.start }}</label>
                        </td>
                        <td style="padding: 0; text-align: center !important"
                            @mouseenter="show_tooltip[segment.id - 1] = true"
                            @mouseleave="show_tooltip[segment.id - 1] = false">
                            <!-- <label>{{ segment.status }}</label> -->
                            <!-- <svg-green-check/>
                             <svg-pause_green/> -->
                            <component :is="icons[segment.id - 1]" />
                            <tool_tip v-show="show_tooltip[segment.id - 1]" :text="statuses[segment.id - 1]" />
                        </td>
                    </tr>
                </table>


                <MediaPlanTable v-show="mode === 'create'" :showMediaPlan="mode === 'create'"
                    :headers="mediaPlanHeaders" :rows="mediaPlanRows" />

                <FinanceTable v-show="mode === 'finance'" :showMediaPlan="mode === 'finance'" :rows="financeRows"
                    :subrows="financeSubRows" />

                <!-- <MediaPlanTable v-show="show_plane_mode" :showMediaPlan="show_plane_mode" :headers="mediaPlanHeaders"
                    :rows="mediaPlansRows" /> -->

                <SettingsPlaneTable v-show="mode === 'settings'" :showMediaPlan="mode === 'settings'"
                    :headers="SettingsPlanHeaders" :rows="settingsPlansRows" />

                <ShowPlaneTable v-show="mode === 'show_plane'" :headers="SettingsPlanHeaders" :rows="showPlansRows" />



                <div v-show="new_user && selected === 'functionality'">
                    <div class="p-r">
                        <div class="txt_input_u input_users_pars p-r settings_user_part">
                            <svg @click="selectFuncPart('new_delivery')" class="input__svg_arrow_u" width="16"
                                height="16" :class="{ rotate_180: func_part === 'new_delivery' }" viewBox="0 0 16 16"
                                fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                                    fill="#6B7280" />
                            </svg>
                            <div class="cntr-row a-c j-b p-r">

                                Создание доставок
                                <switch-func />
                            </div>


                            <div v-show="func_part === 'new_delivery'">
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Добавить доставку
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Импорт CSV
                                    <switch-func />
                                </div>
                            </div>

                        </div>

                        <div class="txt_input_u input_users_pars p-r settings_user_part">
                            <svg @click="selectFuncPart('delivery')" class="input__svg_arrow_u" width="16" height="16"
                                :class="{ rotate_180: show_run_delivery_func }" viewBox="0 0 16 16" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                                    fill="#6B7280" />
                            </svg>
                            <div class="cntr-row a-c j-b p-r">

                                Запуск доставок
                                <switch-func />
                            </div>


                            <div v-show="func_part === 'delivery'">
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Настройка фидов
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Настройка лимитов, ставок, закупки
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Настройка сегментов
                                    <switch-func />
                                </div>
                            </div>

                        </div>

                        <div class="txt_input_u input_users_pars p-r settings_user_part">
                            <svg @click="selectFuncPart('ad')" class="input__svg_arrow_u" width="16" height="16"
                                :class="{ rotate_180: show_ad_func }" viewBox="0 0 16 16" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                                    fill="#6B7280" />
                            </svg>
                            <div class="cntr-row a-c j-b p-r">

                                Управление рекламой
                                <switch-func />
                            </div>


                            <div v-show="func_part === 'ad'">
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Настройка сегментов доставок
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Управление аудиториями
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Список экспортов
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Настройка сегментов доставок
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Сегменты
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Интересы ВК, ВКР и МТ
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Аудитории
                                    <switch-func />
                                </div>
                            </div>

                        </div>

                        <div class="txt_input_u input_users_pars p-r settings_user_part">
                            <svg @click="selectFuncPart('settings')" class="input__svg_arrow_u" width="16" height="16"
                                :class="{ rotate_180: func_part === 'settings' }" viewBox="0 0 16 16" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                                    fill="#6B7280" />
                            </svg>
                            <div class="cntr-row a-c j-b p-r">

                                Настройки
                                <switch-func />
                            </div>


                            <div v-show="func_part === 'settings'">
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Настройки ТГ-чатов
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Настройка аккаунтов и клиентов
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Тип сети
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Пользователи
                                    <switch-func />
                                </div>
                            </div>
                        </div>

                        <div class="txt_input_u input_users_pars p-r settings_user_part">
                            <svg @click="selectFuncPart('stat')" class="input__svg_arrow_u" width="16" height="16"
                                :class="{ rotate_180: func_part === 'stat' }" viewBox="0 0 16 16" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                                    fill="#6B7280" />
                            </svg>
                            <div class="cntr-row a-c j-b p-r">

                                Статистика
                                <switch-func />
                            </div>


                            <div v-show="func_part === 'stat'">
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Доставка
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Индекс
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Сегменты
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Тизеры
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Панель
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Социология
                                    <switch-func />
                                </div>
                            </div>
                        </div>

                    </div>
                </div>

                <div v-show="new_user && selected === 'content'">
                    <div class="p-r">
                        <div class="txt_input_u input_users_pars p-r settings_user_part">

                            <div class="cntr-row a-c p-r" style="justify-content: flex-end;">
                                <div>

                                </div>
                                <div class="cntr-row" style="gap: 8vw">
                                    <label class="text-hide">Просмотр</label>
                                    <label class="text-hide">Создание</label>
                                </div>
                            </div>



                        </div>

                        <div class="txt_input_u input_users_pars p-r settings_user_part">
                            <svg @click="selectFuncPart('delivery')" class="input__svg_arrow_u" width="16" height="16"
                                :class="{ rotate_180: show_run_delivery_func }" viewBox="0 0 16 16" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                                    fill="#6B7280" />
                            </svg>
                            <div class="cntr-row a-c j-b p-r">

                                Индекс 1
                                <div class="cntr-row" style="gap: 9vw">
                                    <switch-func />
                                    <switch-func />
                                </div>
                            </div>


                            <div v-show="func_part === 'delivery'">
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Линия 1 Индекса 1
                                    <div class="cntr-row" style="gap: 9vw">
                                        <switch-func />
                                        <switch-func />
                                    </div>
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Линия 2 Индекса 1
                                    <div class="cntr-row" style="gap: 9vw">
                                        <switch-func />
                                        <switch-func />
                                    </div>
                                </div>
                            </div>

                        </div>

                        <div class="txt_input_u input_users_pars p-r settings_user_part">
                            <svg @click="selectFuncPart('ad')" class="input__svg_arrow_u" width="16" height="16"
                                :class="{ rotate_180: show_ad_func }" viewBox="0 0 16 16" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                                    fill="#6B7280" />
                            </svg>
                            <div class="cntr-row a-c j-b p-r">

                                Индекс 2
                                <switch-func />
                            </div>


                            <div v-show="func_part === 'ad'">
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Линия 1 Индекса 2
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Линия 2 Индекса 2
                                    <switch-func />
                                </div>
                                <div class="txt_input_u cntr-row a-c j-b settings_user_item">
                                    Линия 3 Индекса 2
                                    <switch-func />
                                </div>
                            </div>

                        </div>



                    </div>
                </div>

                <div v-show="new_user" @click="show_modal_is_save = true" class="btn__save-user"
                    :class="{ active_btn_color: active_btn_save }" style="margin-top: 24px;">
                    Сохранить
                </div>

            </div>

            <div class="cntr-row j-b a-c mt-168" v-show="!new_user">
                <div v-show="show_export_success" class="export_success">
                    <svg width="17" height="16" viewBox="0 0 17 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path
                            d="M11.3703 14.7332H8.837C8.46366 14.7332 7.65033 14.6198 7.217 14.1865L5.197 12.6265L5.81033 11.8332L7.877 13.4332C8.04367 13.5932 8.46366 13.7265 8.837 13.7265H11.3703C11.9703 13.7265 12.617 13.2465 12.7503 12.7065L14.3637 7.8065C14.4703 7.51316 14.4503 7.2465 14.3103 7.05316C14.1637 6.8465 13.897 6.7265 13.5703 6.7265H10.9037C10.557 6.7265 10.237 6.57983 10.017 6.3265C9.79033 6.0665 9.69033 5.71983 9.74367 5.35983L10.077 3.21983C10.157 2.8465 9.90367 2.4265 9.54366 2.3065C9.217 2.1865 8.797 2.35983 8.65033 2.57316L5.917 6.63983L5.09033 6.0865L7.82367 2.01983C8.24367 1.39316 9.16367 1.09316 9.88367 1.3665C10.717 1.63983 11.2503 2.55983 11.0637 3.41316L10.737 5.51316C10.7303 5.55983 10.7303 5.6265 10.777 5.67983C10.8103 5.71316 10.857 5.73316 10.9103 5.73316H13.577C14.2303 5.73316 14.797 6.0065 15.1303 6.47983C15.457 6.93983 15.5237 7.5465 15.3103 8.13316L13.717 12.9865C13.4703 13.9532 12.4437 14.7332 11.3703 14.7332Z"
                            fill="#6B7280" />
                        <path
                            d="M4.10352 13.9998H3.43685C2.20352 13.9998 1.60352 13.4198 1.60352 12.2331V5.69977C1.60352 4.51311 2.20352 3.93311 3.43685 3.93311H4.10352C5.33685 3.93311 5.93685 4.51311 5.93685 5.69977V12.2331C5.93685 13.4198 5.33685 13.9998 4.10352 13.9998ZM3.43685 4.93311C2.71018 4.93311 2.60352 5.10644 2.60352 5.69977V12.2331C2.60352 12.8264 2.71018 12.9998 3.43685 12.9998H4.10352C4.83018 12.9998 4.93685 12.8264 4.93685 12.2331V5.69977C4.93685 5.10644 4.83018 4.93311 4.10352 4.93311H3.43685Z"
                            fill="#6B7280" />
                    </svg>

                    <div class="export_success_txt">
                        Выгрузка отчета “Название 1” успешно завершена
                    </div>

                </div>

                <div class="cntr-row" v-show="false">
                    <div class="grey-box w-97 h-40 cntr-row a-c">
                        <svg v-show="!is_settings_mode" class="ml-16" width="8" height="14" viewBox="0 0 8 14"
                            fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M7.35404 0.646009C7.4006 0.692455 7.43754 0.74763 7.46275 0.808375C7.48796 0.86912 7.50093 0.934242 7.50093 1.00001C7.50093 1.06578 7.48796 1.1309 7.46275 1.19164C7.43754 1.25239 7.4006 1.30756 7.35404 1.35401L1.70704 7.00001L7.35404 12.646C7.44793 12.7399 7.50067 12.8672 7.50067 13C7.50067 13.1328 7.44793 13.2601 7.35404 13.354C7.26015 13.4479 7.13281 13.5006 7.00004 13.5006C6.86726 13.5006 6.73993 13.4479 6.64604 13.354L0.646039 7.35401C0.599476 7.30756 0.562533 7.25239 0.537326 7.19164C0.51212 7.1309 0.499146 7.06578 0.499146 7.00001C0.499146 6.93424 0.51212 6.86912 0.537326 6.80838C0.562533 6.74763 0.599476 6.69245 0.646039 6.64601L6.64604 0.646009C6.69248 0.599446 6.74766 0.562503 6.80841 0.537296C6.86915 0.51209 6.93427 0.499115 7.00004 0.499115C7.06581 0.499115 7.13093 0.51209 7.19167 0.537296C7.25242 0.562503 7.30759 0.599446 7.35404 0.646009Z"
                                fill="#6B7280" />
                        </svg>
                        <svg v-show="is_settings_mode" class="ml-16" width="16" height="16" viewBox="0 0 16 16"
                            fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M11.3539 1.64689C11.4005 1.69334 11.4374 1.74852 11.4626 1.80926C11.4878 1.87001 11.5008 1.93513 11.5008 2.00089C11.5008 2.06666 11.4878 2.13178 11.4626 2.19253C11.4374 2.25327 11.4005 2.30845 11.3539 2.35489L5.70692 8.00089L11.3539 13.6469C11.4478 13.7408 11.5005 13.8681 11.5005 14.0009C11.5005 14.1337 11.4478 14.261 11.3539 14.3549C11.26 14.4488 11.1327 14.5015 10.9999 14.5015C10.8671 14.5015 10.7398 14.4488 10.6459 14.3549L4.64592 8.35489C4.59935 8.30845 4.56241 8.25327 4.5372 8.19253C4.512 8.13178 4.49902 8.06666 4.49902 8.00089C4.49902 7.93513 4.512 7.87001 4.5372 7.80926C4.56241 7.74852 4.59935 7.69334 4.64592 7.64689L10.6459 1.64689C10.6924 1.60033 10.7475 1.56339 10.8083 1.53818C10.869 1.51297 10.9341 1.5 10.9999 1.5C11.0657 1.5 11.1308 1.51297 11.1916 1.53818C11.2523 1.56339 11.3075 1.60033 11.3539 1.64689Z"
                                fill="#6B7280" fill-opacity="0.5" />
                        </svg>

                        <div class="text-2 ml-11" :class="{ disable_color: is_settings_mode }">Назад</div>
                    </div>

                    <div class="num-page-box num-page-txt a-c cntr-row j-c"
                        :class="{ disable_color: is_settings_mode }">1
                    </div>

                    <div class="blue-box a-c cntr-row j-c text-white ml-10"
                        :class="{ disable_bg_color_num_page: is_settings_mode, disable_color_selected_page: is_settings_mode }">
                        2
                    </div>

                    <div class="num-page-box num-page-txt a-c cntr-row j-c"
                        :class="{ disable_color: is_settings_mode }">3
                    </div>

                    <div class="num-page-box num-page-txt a-c cntr-row j-c"
                        :class="{ disable_color: is_settings_mode }">4
                    </div>

                    <div class="num-page-box num-page-txt a-c cntr-row j-c"
                        :class="{ disable_color: is_settings_mode }">...
                    </div>
                    <div class="num-page-box num-page-txt a-c cntr-row j-c"
                        :class="{ disable_color: is_settings_mode }">100
                    </div>
                    <div class="grey-box w-98 h-40 cntr-row a-c ml-10 btn_onwards cur-pointer">

                        <div class="text-2 ml-16 " :class="{ disable_color: is_settings_mode }">Далее</div>

                        <svg v-show="!is_settings_mode" class="ml-11" width="8" height="14" viewBox="0 0 8 14"
                            fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M0.646039 0.646009C0.692485 0.599446 0.74766 0.562503 0.808405 0.537296C0.869151 0.51209 0.934272 0.499115 1.00004 0.499115C1.06581 0.499115 1.13093 0.51209 1.19167 0.537296C1.25242 0.562503 1.30759 0.599446 1.35404 0.646009L7.35404 6.64601C7.4006 6.69245 7.43754 6.74763 7.46275 6.80838C7.48796 6.86912 7.50093 6.93424 7.50093 7.00001C7.50093 7.06578 7.48796 7.1309 7.46275 7.19164C7.43754 7.25239 7.4006 7.30756 7.35404 7.35401L1.35404 13.354C1.26015 13.4479 1.13281 13.5006 1.00004 13.5006C0.867263 13.5006 0.739926 13.4479 0.646039 13.354C0.552152 13.2601 0.499407 13.1328 0.499407 13C0.499407 12.8672 0.552152 12.7399 0.646039 12.646L6.29304 7.00001L0.646039 1.35401C0.599476 1.30756 0.562533 1.25239 0.537326 1.19164C0.51212 1.1309 0.499146 1.06578 0.499146 1.00001C0.499146 0.934242 0.51212 0.86912 0.537326 0.808375C0.562533 0.74763 0.599476 0.692455 0.646039 0.646009Z"
                                fill="#6B7280" />
                        </svg>
                        <svg v-show="is_settings_mode" class="ml-11" width="16" height="16" viewBox="0 0 16 16"
                            fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M4.64592 1.64689C4.69236 1.60033 4.74754 1.56339 4.80828 1.53818C4.86903 1.51297 4.93415 1.5 4.99992 1.5C5.06568 1.5 5.13081 1.51297 5.19155 1.53818C5.2523 1.56339 5.30747 1.60033 5.35392 1.64689L11.3539 7.64689C11.4005 7.69334 11.4374 7.74852 11.4626 7.80926C11.4878 7.87001 11.5008 7.93513 11.5008 8.00089C11.5008 8.06666 11.4878 8.13178 11.4626 8.19253C11.4374 8.25327 11.4005 8.30845 11.3539 8.35489L5.35392 14.3549C5.26003 14.4488 5.13269 14.5015 4.99992 14.5015C4.86714 14.5015 4.7398 14.4488 4.64592 14.3549C4.55203 14.261 4.49929 14.1337 4.49929 14.0009C4.49929 13.8681 4.55203 13.7408 4.64592 13.6469L10.2929 8.00089L4.64592 2.35489C4.59935 2.30845 4.56241 2.25327 4.5372 2.19253C4.512 2.13178 4.49902 2.06666 4.49902 2.00089C4.49902 1.93513 4.512 1.87001 4.5372 1.80926C4.56241 1.74852 4.59935 1.69334 4.64592 1.64689Z"
                                fill="#6B7280" fill-opacity="0.5" />
                        </svg>

                    </div>
                </div>

                <div class="cntr-row a-c" v-show="false">
                    <div class="text-2" :class="{ disable_color: is_settings_mode }">Показать</div>
                    <div @click="show_selecter_page = !show_selecter_page"
                        class="btn_pagination grey-box w-113 h-40 cntr-row a-c j-b ml-11">
                        <div v-show="show_selecter_page" class="cntr_select_page"><select-page /></div>

                        <div class="text-3 ml-11" :class="{ disable_color: is_settings_mode }">10</div>

                        <svg v-show="!is_settings_mode" class="mr-16" width="12" height="8" viewBox="0 0 12 8"
                            fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M6.30969 6.93476C6.26905 6.9755 6.22077 7.00783 6.16762 7.02988C6.11446 7.05194 6.05748 7.06329 5.99994 7.06329C5.94239 7.06329 5.88541 7.05194 5.83226 7.02988C5.77911 7.00783 5.73083 6.9755 5.69019 6.93476L0.440187 1.68476C0.358037 1.60261 0.311884 1.49119 0.311884 1.37501C0.311884 1.25883 0.358037 1.14741 0.440187 1.06526C0.522337 0.98311 0.633758 0.936958 0.749938 0.936958C0.866116 0.936958 0.977537 0.98311 1.05969 1.06526L5.99994 6.00639L10.9402 1.06526C11.0223 0.983111 11.1338 0.936959 11.2499 0.936959C11.3661 0.936959 11.4775 0.983111 11.5597 1.06526C11.6418 1.14741 11.688 1.25883 11.688 1.37501C11.688 1.49119 11.6418 1.60261 11.5597 1.68476L6.30969 6.93476Z"
                                fill="#374151" />
                        </svg>
                        <svg v-show="is_settings_mode" class="mr-16" width="14" height="8" viewBox="0 0 14 8"
                            fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M0.645917 0.646894C0.692363 0.60033 0.747539 0.563387 0.808284 0.538181C0.869029 0.512974 0.93415 0.5 0.999917 0.5C1.06568 0.5 1.13081 0.512974 1.19155 0.538181C1.2523 0.563387 1.30747 0.60033 1.35392 0.646894L6.99992 6.29389L12.6459 0.646894C12.6924 0.600406 12.7476 0.563529 12.8083 0.53837C12.8691 0.513211 12.9342 0.500262 12.9999 0.500262C13.0657 0.500262 13.1308 0.513211 13.1915 0.53837C13.2522 0.563529 13.3074 0.600406 13.3539 0.646894C13.4004 0.693381 13.4373 0.748571 13.4624 0.80931C13.4876 0.870049 13.5005 0.93515 13.5005 1.00089C13.5005 1.06664 13.4876 1.13174 13.4624 1.19248C13.4373 1.25322 13.4004 1.30841 13.3539 1.35489L7.35392 7.35489C7.30747 7.40146 7.2523 7.4384 7.19155 7.46361C7.13081 7.48881 7.06568 7.50179 6.99992 7.50179C6.93415 7.50179 6.86903 7.48881 6.80828 7.46361C6.74754 7.4384 6.69236 7.40146 6.64592 7.35489L0.645917 1.35489C0.599354 1.30845 0.562411 1.25327 0.537205 1.19253C0.511998 1.13178 0.499023 1.06666 0.499023 1.00089C0.499023 0.935126 0.511998 0.870005 0.537205 0.80926C0.562411 0.748515 0.599354 0.693339 0.645917 0.646894Z"
                                fill="#6B7280" fill-opacity="0.5" />
                        </svg>


                    </div>
                </div>
            </div>

            <div class="cntr_message_upload">
                <SvgLike />
                Выгрузка медиаплана успешно завершена
            </div>
        </div>
    </div>
</template>



<script>

import PartLeftListDelivers from './PartLeftListDelivers.vue'
import SelecterPage from '../elements/SelecterPage.vue'
// import ModalIFiltersMonitoring from '../settings/ModalIFiltersMonitoring.vue'
import ModalIFiltersMonitoringSegments from '../settings/ModalIFiltersMonitoringSegments.vue'
import ModalIFiltersReports from '../settings/ModalIFiltersReports.vue'
import ModalNewInterest from '../settings/ModalNewInterest.vue'
import ModalDelete from '../settings/ModalDelete.vue'
import SvgFidcheck from '../svg/SvgFidcheck'
import SelecterRoles from '../settings/SelecterRoles.vue'
import SwitchFunc from '../svg/SwitchFunc.vue'
import ModalIsAddUser from '../settings/ModalIsAddUser.vue'
import DataCalendar from '../svg/DataCalendar.vue'
import ModalListDelivers from '../settings/ModalListDelivers.vue'
import SelecterNet from '../elements/SelecterNet.vue'
import SvgGreenCheck from '../svg/SvgGreenCheck.vue'
import SvgCancelGrey from '../svg/SvgCancelGrey.vue'
import ToolTip from './media_plane/ToolTip.vue'
import SvgPauseGreen from '../svg/SvgPauseGreen.vue'
import MediaPlanTable from './media_plane/MediaPlanTable.vue'
import SvgCalendar from './media_plane/SvgCalendar.vue'
import SvgEdit from './media_plane/SvgEdit.vue'
import SvgReserve from './media_plane/SvgReserve.vue'
import SvgSquare from './media_plane/SvgSquare.vue'
import SvgSquareCheck from './media_plane/SvgSquareCheck.vue'
import SelecterDateTime from './media_plane/SelecterDateTime.vue'
import InputMediaplane from './media_plane/InputMediaplane.vue'
import FinanceTable from './media_plane/FinanceTable.vue'
// import ShowMediaPlanTable from './media_plane/SettingsPlaneTable.vue'
import SettingsPlaneTable from './media_plane/SettingsPlaneTable.vue'
import SvgSave from './media_plane/SvgSave.vue'
import ShowPlaneTable from './media_plane/ShowPlaneTable.vue'
import ModalIsSave from './media_plane/ModalIsSave.vue'
import ModalWarning from './media_plane/ModalWarning.vue'
import SvgLike from './media_plane/SvgLike.vue'
import SvgRefreshRed from './media_plane/SvgRefreshRed.vue'
import SvgCalendarBlue from './media_plane/SvgCalendarBlue.vue'

// import SvgCaution from '../svg/SvgCaution.vue'
// import SvgGreenLightning from '../svg/SvgGreenLightning.vue'
// import SvgGreenPause from '../svg/SvgGreenPause.vue'
// import SvgRedPause from '../svg/SvgRedPause.vue'
// import SvgRedPlay from '../svg/SvgRedPlay.vue'
// import IconWithTooltip from '../elements/IconWithTooltip.vue'



export default {
    name: 'MediaPlaning',
    data() {
        return {
            statuses: ['Завершен', 'В работе', 'Ожидание'],
            mediaPlanRows: [
                {
                    index: "Индекс",
                    line: "Линия",
                    views_day: "7 300 000",
                    views_month: "219 000 000",
                    ctr: "0,1",
                },
            ],
            mediaPlansRows: [
                {
                    index: "Индекс",
                    line: "Линия",
                    views_day: "7 300 000",
                    views_month: "219 000 000",
                    ctr: "0,1",
                },
                {
                    index: "Индекс",
                    line: "Линия",
                    views_day: "7 300 000",
                    views_month: "219 000 000",
                    ctr: "0,1",
                },
                {
                    index: "Индекс",
                    line: "Линия",
                    views_day: "7 300 000",
                    views_month: "219 000 000",
                    ctr: "0,1",
                },
            ],
            settingsPlansRows: [
                {
                    index: "VK",
                    line: "0%",
                    views_day: "10%",
                },
                {
                    index: "VK",
                    line: "0%",
                    views_day: "10%",
                },
                {
                    index: "VK",
                    line: "0%",
                    views_day: "10%",
                },
            ],
            showPlansRows: [
                {
                    index: "Индекс 1",
                    line: "Линия 1",
                    views_day: "300 000",
                    views_month: "9 300 000",
                    ctr: "0,01",
                    ctr2: "15 326, 40",
                    dev: '269 000',
                    col8: '9 560 110',
                    col9: '0,01',
                    col10: '17 000',
                    col11: '120,03%',
                    col12: '100,00%',
                    col13: '110,02%',
                },
                {
                    index: "Индекс 1",
                    line: "Линия 1",
                    views_day: "300 000",
                    views_month: "9 300 000",
                    ctr: "0,01",
                    ctr2: "15 326, 40",
                    dev: '269 000',
                    col8: '9 560 110',
                    col9: '0,01',
                    col10: '17 000',
                    col11: '120,03%',
                    col12: '100,00%',
                    col13: '110,02%',
                },
                {
                    index: "Индекс 1",
                    line: "Линия 1",
                    views_day: "300 000",
                    views_month: "9 300 000",
                    ctr: "0,01",
                    ctr2: "15 326, 40",
                    dev: '269 000',
                    col8: '9 560 110',
                    col9: '0,01',
                    col10: '17 000',
                    col11: '120,03%',
                    col12: '100,00%',
                    col13: '110,02%',
                },
            ],
            financeRows: [
                {
                    index: "Индекс 1",
                    line: "Все линии",
                    views_day: "VK",
                    views_month: "VKv2",
                    ctr: "КПЭ показы, расчет",
                    ctr2: "КПЭ показы, план",
                    dev: 'Отклонение от плана, %'
                },
                {
                    index: "Индекс 1",
                    line: "Все линии",
                    views_day: "VK",
                    views_month: "VKv2",
                    ctr: "КПЭ показы, расчет",
                    ctr2: "КПЭ показы, план",
                    dev: 'Отклонение от плана, %'
                },
            ],
            financeSubRows: [
                {
                    index: "Показы (день)",
                    line: "7 300 000",
                    views_day: "7 300 000",
                    views_month: "14 600 000",
                    ctr: "15 000 000",
                    ctr2: "-2,66%",
                },
                {
                    index: "Показы (день)",
                    line: "7 300 000",
                    views_day: "7 300 000",
                    views_month: "14 600 000",
                    ctr: "15 000 000",
                    ctr2: "-2,66%",
                },
                {
                    index: "Показы (день)",
                    line: "7 300 000",
                    views_day: "7 300 000",
                    views_month: "14 600 000",
                    ctr: "15 000 000",
                    ctr2: "-2,66%",
                },
            ],

            mediaPlanHeaders: [
                { text: "Индекс", width: "120px" },
                { text: "Линия", width: "120px" },
                { text: "КПЭ показы (день), план", width: "197px" },
                { text: "КПЭ показы (месяц), план", width: "197px" },
                { text: "КПЭ CTR,%", width: "150px" },
            ],
            SettingsPlanHeaders: [
                { text: "Сеть", width: "191px" },
                { text: "НДС", width: "191px" },
                { text: "Скидка", width: "191px" },
            ],
            icons: [SvgGreenCheck, SvgPauseGreen, SvgRefreshRed],
            show_segments_list_id: false,
            text_list_delivers: 'Список доставок/индексов',
            text_list_id: 'Список ID',
            error_export: false,
            selected: 'content',
            func_part: '', //delivary ad, settings, stat
            password: '',
            headers_report: [
                { text: "Формат", width: "191px" },
                { text: "Сеть", width: "191px" },
                { text: "Дата заведения в сеть", width: "191px" },
                { text: "Дата заведения в системе", width: "191px" },
                { text: "Кто завел", width: "191px" },
                { text: "Кто завел", width: "191px" },
                { text: "Сегменты в системе", width: "191px" },
                { text: "Сегменты в сети", width: "191px" },
                { text: "Внешний ID", width: "191px" },
                { text: "Ссылки на объявления", width: "191px" },
                { text: "Объем сегмента", width: "191px" },
                { text: "Наличие ошибки", width: "191px" },
            ],
            segments: [
                {
                    id: 1,
                    plane: 'Новый медиаплан 1',
                    status: 'check',
                    period: 'Август 2024',
                    start: '10:38 16.07.2024',
                    end: '09.11.2023-11.12.2024',
                    is_check: false
                },
                {
                    id: 2,
                    plane: 'Новый медиаплан 1',
                    status: 'check',
                    period: 'Август 2024',
                    start: '10:38 16.07.2024',
                    end: '09.11.2023-11.12.2024',
                    is_check: false
                },
                {
                    id: 3,
                    plane: 'Новый медиаплан 3',
                    status: 'check',
                    period: 'Август 2024',
                    start: '10:38 16.07.2024',
                    end: '09.11.2023-11.12.2024',
                    is_check: true
                },
            ],
            reports: [
                {
                    id: 1,
                    index: 'aaa 1',
                    status: '1',
                    date_create: '09.11.2023-11.12.2024',
                    segment: 'Россия 18+',
                    format: 'Пост',
                    prioritet: 1,
                    tag: 'Новый тэг',
                    line: 'Линия 1',
                    line2: 'Линия 2',
                    segment_volume: 10000,
                    shows: 10,
                },

            ],
            my_width: '100%',
            is_check: true,
            active_btn_save: true,
            show_export_success: false,
            show_modal_filters: false,
            show_report_filters: false,
            show_modal_is_save: false,
            show_modal_list_delivers: false,
            show_modal_is_del: false,
            show_modal_new_segment: false,
            show_modal_new_interest: false,
            show_modal_delete: false,
            show_selecter: false,
            show_selecter_net: false,
            input_dis_geo_active_bg: false,
            new_user: false,
            show_selecter_page: false,
            is_settings_mode: false,
            report_mode: false,
            addexport_mode: false,
            create_plane_mode: false,
            mode: 'main',
            finance_mode: false,
            sort_states: [0, 1, 2],
            sort_segment_ind: 0,
            sort_period_ind: 0,

            config_mode: false,
            settings_mode: false, // PASSWORD CHANGE MODE


            show_table_select_gender: false,

            show_selecter_net_list: [false, false, false, false, false, false, false, false, false, false, false],
            showPassword: false,
            show_select_item_interest: false,
            show_select_item: false,
            show_tooltip: [false, false, false],
            show_run_delivery_func: false,
            show_ad_func: false,

            show_selecter_datetime: false,
            show_input_name_plane: false,
            show_input_reserve: false,
            is_consider_click: false,
            show_plane_mode: false,
            is_results: false,
        }
    },
    components: {
        'part-left': PartLeftListDelivers,
        'modal-filters-users': ModalIFiltersMonitoringSegments,
        'modal-filters-reports': ModalIFiltersReports,
        'select-page': SelecterPage,
        'selecter-net': SelecterNet,
        'modal_new_interest': ModalNewInterest,
        'modal-delete': ModalDelete,
        ModalIsSave,
        ModalWarning,
        'svg-fidcheck': SvgFidcheck,
        'selecter-role': SelecterRoles,
        'switch-func': SwitchFunc,
        'modal-isadd-user': ModalIsAddUser,
        'modal-list-delivers': ModalListDelivers,
        'svg-cancel-grey': SvgCancelGrey,
        'svg-data': DataCalendar,
        'svg-green-check': SvgGreenCheck,
        'svg-pause_green': SvgPauseGreen,
        'tool_tip': ToolTip,
        MediaPlanTable,
        SvgCalendar,
        SvgEdit,
        SvgReserve,
        SvgSquare,
        SvgSquareCheck,
        SvgSave,
        SvgLike,
        SelecterDateTime,
        InputMediaplane,
        FinanceTable,
        SettingsPlaneTable,
        ShowPlaneTable,
        SvgCancelGrey,
        SvgRefreshRed,
        SvgCalendarBlue
    },
    computed: {
        passwordFieldType() {
            return this.showPassword ? 'text' : 'password';
        }
    },
    methods: {
        toggleSegmentsList() {
            this.show_segments_list_id = !this.show_segments_list_id;
        },
        getThStyle(head) {
            if (head === "Подозрительный прирост показов") {
                return { width: '210px' };
            } else {
                return { width: '191px' };
            }
        },
        selectMenuItem(item) {
            this.selected = item; // Изменяем значение переменной на выбранный пункт меню
        },
        selectFuncPart(part) {
            this.func_part = this.func_part === part ? '' : part
        },
        updateVariable(net) {
            return (selectedInterest) => {
                // Обновляем поле type выбранного объекта net
                this.show_selecter_net_list[net.id - 1] = false;
                // console.log('selectedInterest', selectedInterest, net)
                // net.type = selectedInterest;
                this.nets[net.id - 1].type = selectedInterest
                // console.log('selectedInterest', selectedInterest, net)
                this.config_mode = true

            };
        },
        togglePasswordVisibility() {
            this.showPassword = !this.showPassword;
        }
    }
}

</script>

<style scoped>
.border_blue {
    border-color: #3B82F6 !important;
}
.cntr_message_upload {
    border: 1px solid #27AE60;
    border-radius: 8px;
    position: absolute; 
    bottom: 154; 
    right: 10px; 
    display: flex;
    width: 224px;
    padding: 12px 18px;
    align-items: center
}
.border_red {
    border-color: #F87171
}

.mt-13 {
    margin-top: 13px;
}

.input_add_export_segments {
    border-radius: 6px;
    border: 1px solid #E5E7EB;
    background: #FFF;

    width: 100%;
    height: 44px;
    box-sizing: border-box;

    padding-left: 20px;
    color: #1F2937 !important
}

.input_add_export_segments:focus {
    background-color: white !important;
}

.input_add_export {
    border-radius: 6px;
    border: 1px solid #E5E7EB;
    background: #FFF;

    width: 100%;
    height: 44px;
    box-sizing: border-box;

    padding-left: 20px;
    color: #6B7280 !important
}

.input_add_export:hover {
    background: #F3F4F6;
}

.input_add_export:focus {
    background: #F3F4F6;
}

.cntr_addexport {
    width: 100%;
    height: 435px;
    flex-shrink: 0;

    border-radius: 8px;
    border: 1px solid #E5E7EB;
    background: #FFF;

    /* Drop Shadow/lg */
    box-shadow: 0px 4px 3px 0px rgba(0, 0, 0, 0.10), 0px 10px 8px 0px rgba(0, 0, 0, 0.04);
    z-index: 20;

    padding: 45px 75px 0 45px;
    box-sizing: border-box;
}

.report_table {
    width: max-content !important;
}

.td__segment_settings {
    overflow-x: scroll;
    white-space: nowrap;
}

.mon_seg_add_exp_part1 {
    flex: 4;
    border-top-right-radius: 0;
    /* Оставляем правые углы острыми */
    border-bottom-right-radius: 0;
}

/* Див занимает 1 часть из 5 */
.mon_seg_add_exp_part2 {
    flex: 1;
    border-top-left-radius: 0;
    /* Оставляем левые углы острыми */
    border-bottom-left-radius: 0;
    align-items: center;
    display: flex;
    cursor: pointer;
    /* transition: background-color 1s ease; */
}

.mon_seg_add_exp_part2:hover {
    background: transparent !important;
}

.mon_seg_add_exp_part2:active {
    background-color: #3B82F6 !important;
    color: #fff !important;
}

td {
    text-align: left;
    padding-left: 20px;
    border: 1px solid var(--gray-200, #E5E7EB);
    position: relative;
    height: 44px;

}

th {
    border: 1px solid var(--gray-200, #E5E7EB);
    position: relative;
    height: 44px;
    cursor: pointer
}

th:nth-child(1),
td:nth-child(1) {
    width: 60px;
}

th:nth-child(2),
td:nth-child(2) {
    /* max-width: 323px; */
    width: 191px;
    box-sizing: border-box;
    padding: 18px 0 18px 20px !important;
}

th:nth-child(2)::-webkit-scrollbar,
td:nth-child(2)::-webkit-scrollbar {
    width: 4px !important;
}

/* ::-webkit-scrollbar-thumb {
    border-radius: 999px;
    background: var(--gray-200, #E5E7EB);
} */


th:nth-child(3),
td:nth-child(3) {
    width: 191px;
    text-align: left !important;
    /* padding: 0 !important; */
}

th:nth-child(4),
td:nth-child(4) {
    width: 191px;
    text-align: left;
}

th:nth-child(5),
td:nth-child(5) {
    width: 82px;
    text-align: left;
}

th:nth-child(6),
td:nth-child(6) {
    width: 191px;
    text-align: left;
}

th:nth-child(7),
td:nth-child(7) {
    width: 191px;
}

.h_75 {
    height: 75vh !important;
}

.settings_user_part {
    padding-right: 14px;
    padding-left: 36px !important;
    height: auto !important;
    margin-top: 8px;
}

.settings_user_item {
    padding-left: 20px;
    margin-top: 8px;
}

.input_non_empty {
    border-color: #F87171 !important;
    color: #F87171 !important;
}

.active_btn_color {
    opacity: 1 !important;
    color: #fff !important;
}

.btn__save-user {
    background-color: #3B82F6;
    opacity: 0.5;
    height: 46px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 16px;
    font-weight: 400;
    color: rgba(255, 255, 255, 0.5);
    border-radius: 6px;
    z-index: 0;
    cursor: pointer;
}

.txt_select_item {
    color: #6B7280;

    /* XS/Medium */
    font-family: Inter;
    font-size: 12px;
    font-style: normal;
    font-weight: 500;
    line-height: 16px;
    /* 133.333% */
    letter-spacing: 0.06px;
}

.selected_item {
    position: absolute;
    bottom: -50px;

    display: flex;
    align-items: center;
    width: 100%;
    height: 48px;
    padding: 8px;

    border-radius: 8px;
    border: 1px solid #E5E7EB;
    background: #F3F4F6;

    /* Drop Shadow/lg */
    box-shadow: 0px 4px 3px 0px rgba(0, 0, 0, 0.10), 0px 10px 8px 0px rgba(0, 0, 0, 0.04);
    box-sizing: border-box;
    z-index: 15;
}

.input__svg_arrow {
    position: absolute;
    right: 20px;
    top: 50%;
    transform: translateY(-50%);
    cursor: pointer;
}

.input__svg_arrow_u {
    position: absolute;
    left: 15px;
    top: 22px;
    transform: translateY(-50%);
    cursor: pointer;
}

.input_active_bg {
    background: #F3F4F6;
}

.txt_input_u {
    color: var(--gray-800, #1F2937);

    /* SM/Medium */
    font-family: Inter;
    font-size: 14px;
    font-style: normal;
    font-weight: 400;
    line-height: 20px;
    /* 142.857% */
    letter-spacing: 0.07px;
}


.txt_input {
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

.txt_input_delivers {
    font-family: Inter;
    font-size: 14px;
    font-weight: 500;
    line-height: 16px;
    letter-spacing: 0.005em;
    text-align: left;
    color: #1F2937
}

.input_users_pars {
    border-radius: 6px;
    border: 1px solid #E5E7EB;
    background: #FFF;

    width: 100%;
    height: 46px;
    padding-top: 11px;
    padding-bottom: 11px;
    box-sizing: border-box;

    padding-left: 20px;
}

.cntr_settings {
    border-radius: 6px;
    border: 1px solid #E5E7EB;
    background: #FFF;

    width: 45vw;
    /* height: 46px; */
    padding: 40px;
    box-sizing: border-box;
}

.p-r {
    position: relative;
}

.mt-24 {
    margin-top: 24px;
}

.txt_label {
    color: #000;
    font-family: Inter;
    font-size: 16px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    letter-spacing: 0.08px;
}

.input_label_new_user {
    display: block;
    text-align: left;
    width: 100%;
    margin-bottom: 7px;
}

.input_label {
    display: block;
    text-align: left;
    width: 100%;
    height: 37px;
}

.sub_menu_ssd {
    margin-top: 31px;
}

.g-26 {
    gap: 26px;
}

.text__sub_menu_ssd_dis {
    color: var(--d-9-d-9-d-9, #6B7280);
    font-family: Inter;
    font-size: 15px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    letter-spacing: 0.18px;
    box-sizing: border-box;
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
    box-sizing: border-box;
    /* border-bottom: solid 2px #6B7280; */
}

.active_color_link {
    color: #3B82F6;
}

.td_input_report {
    position: absolute;
    top: 12px;
    outline: none;
    border: none;
    color: var(--gray-800, #1F2937);

    /* SM/Medium */
    font-family: Inter;
    font-size: 14px;
    font-style: normal;
    font-weight: 500;
    line-height: 20px;
    /* 142.857% */
    letter-spacing: 0.07px;
    background-color: white !important;

}

.td_input_report::placeholder {
    font-family: Inter;
    font-size: 12px;
    font-style: normal;
    font-weight: 500;
    line-height: 16px;
}

.txt_all {
    color: var(--gray-500, #6B7280);

    margin: 12px;
    /* XS/Medium */
    font-family: Inter;
    font-size: 12px;
    font-style: normal;
    font-weight: 500;
    line-height: 16px;
    /* 133.333% */
    letter-spacing: 0.06px;
}


.input_find {
    border-radius: 6px;
    border: 1px solid var(--gray-200, #E5E7EB);
    background: var(--white-white, #FFF);
    height: 28px;
    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);
    width: 100%;
    padding: 14px 16px 14px 36px;
    box-sizing: border-box;
    outline: none;
}

.cntr_input_find {
    position: absolute;
    width: 100%;
    height: 68px;
    bottom: -76px;
    left: 0;

    border-radius: 8px;
    border: 1px solid var(--gray-200, #E5E7EB);
    background: var(--white-white, #FFF);

    /* Drop Shadow/lg */
    box-shadow: 0px 4px 3px 0px rgba(0, 0, 0, 0.10), 0px 10px 8px 0px rgba(0, 0, 0, 0.04);
}

.sub_cntr_input_find {
    position: relative;
    margin: 8px;
}

.find_svg {
    position: absolute;
    top: 50%;
    left: 16px;
    transform: translateY(-50%);
}

.td__net_svg_arrow {
    /* position: absolute; */
    /* top: 50%; */
    /* transform: translateY(-50%); */
    /* left: 20px; */
    cursor: pointer;
    margin-right: 14px;
}

.export_success {
    box-sizing: border-box;
    position: absolute;
    right: 0;
    top: -34px;
    display: flex;
    /* width: 250px; */
    height: 56px;
    padding: 17px;
    justify-content: center;
    align-items: center;
    /* gap: 6.966px; */
    flex-shrink: 0;
    border-radius: 5.224px;
    border: 0.871px solid #27AE60;
    background-color: #fff;
    gap: 7px;
}

.export_success_txt {
    color: #6B7280;
    font-family: Inter;
    font-size: 13.061px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    letter-spacing: 0.065px;
    width: 195px;
}








.td__svg {
    cursor: pointer
}

.td__svg:hover .td__svg_cross {
    fill: #F87171 !important
}



.segment_menu {
    display: flex;
    justify-content: space-between;
    gap: 8px;
}

.report_menu {
    display: flex;
    justify-content: flex-end;
    gap: 8px;
    width: 100%;
    box-sizing: border-box;
}

.menu_create {
    padding: 0 16px;
    margin-right: 8px;
    cursor: pointer;
}

.svg_check {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translateY(-50%) translateX(-50%);
    /* transform: translateX(-50%); */
}

.menu_create:hover {
    background-color: #F3F4F6;
}

.menu_cancel {
    padding: 0 16px;
    margin-right: 8px;
}

.menu_cancel:hover {
    background-color: #F3F4F6;
}

.menu_settings {
    padding: 0 16px;
    margin-right: 8px;
}

.menu_settings:hover {
    background-color: #F3F4F6;
}

.menu_filters {
    padding: 0 16px;
}

.menu_filters:hover {
    background-color: #F2F7FF
}

.btn_settings {
    background-color: #F2F7FF;
    padding: 0 16px;
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

.h_svg_mediaplane {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    left: 55%;
}

.selected_color {
    color: #3B82F6 !important
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
    padding-right: 2px;
    overflow: scroll;
    width: 75vw;
    height: 65vh;
    position: relative;
}

.cntr-table::-webkit-scrollbar {
    width: 6px;
}


/* TABLES */

/* td:not(:first-child),
th:not(:first-child) {

    width: 15vw;
} */
.bg-white {
    background: white !important;
}



/* th:hover {
    background-color: #F3F4F6;
} */

.header1 {
    position: sticky;
    top: 0px;
    background-color: #fff;
    z-index: 11;
    border: 1px solid var(--gray-200, #E5E7EB);
}



.new_deliver td {
    color: #F87171;
    border: 1px solid #F87171 !important;
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
    border-spacing: 0;
    /* width: 107vw; */
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

.text-hide {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 16px;
    text-align: right;

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

/* INPUT RANGE */

input[type="range"] {
    -webkit-appearance: none;
    /* margin-right: 15px; */
    /* width: 15.6vw; */
    height: 4px;
    /* background: rgba(255, 255, 255, 0.6); */
    /* border-radius: 5px; */
    border-radius: 999px;
    background: var(--gray-200, #E5E7EB);
    background-image: linear-gradient(#3B82F6, #3B82F6);

    background-size: 70% 100%;
    background-repeat: no-repeat;
}

/* Input Thumb */
input[type="range"]::-webkit-slider-thumb {
    border: 3px solid #FFFFFF;
    margin-top: -2px;
    -webkit-appearance: none;
    height: 13px;
    width: 13px;
    border-radius: 50%;
    background: #FFFFFF;
    cursor: ew-resize;
    box-shadow: 0 0 2px 0 #555;
    transition: background .3s ease-in-out;
}

input[type="range"]::-moz-range-thumb {
    -webkit-appearance: none;
    height: 10px;
    width: 10px;
    border-radius: 50%;
    background: #FFFFFF;
    cursor: ew-resize;
    box-shadow: 0 0 2px 0 #555;
    transition: background .3s ease-in-out;
}

input[type="range"]::-ms-thumb {
    -webkit-appearance: none;
    height: 20px;
    width: 20px;
    border-radius: 50%;
    background: #FFFFFF;
    cursor: pointer;
    box-shadow: 0 0 2px 0 #555;
    transition: background .3s ease-in-out;
}

input[type="range"]::-webkit-slider-thumb:hover {
    background: #FFFFFF;
}

input[type="range"]::-moz-range-thumb:hover {
    background: #FFFFFF;
}

input[type="range"]::-ms-thumb:hover {
    background: #FFFFFF;
}

/* Input Track */
input[type=range]::-webkit-slider-runnable-track {
    -webkit-appearance: none;
    box-shadow: none;
    border: none;
    background: transparent;
}

input[type=range]::-moz-range-track {
    -webkit-appearance: none;
    box-shadow: none;
    border: none;
    background: transparent;
}

input[type="range"]::-ms-track {
    -webkit-appearance: none;
    box-shadow: none;
    border: none;
    background: transparent;
}



input {
    outline: none;
}
</style>