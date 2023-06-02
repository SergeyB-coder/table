<template>
    <div class="main__modal">
        <div class="main__modal_title">Настроить</div>

        <div class="line mt-10">
        </div>

        <div class="main__modal_label mt-20">Отображаемые индексы</div>
        <div class="main__modal_selecter mt-10 cur_p" @click="show_dd_indexes = !show_dd_indexes">
            <!-- <div class="text-2 ml-11">Выбрать</div> -->

            <div class="main__modal_cntr_selected_indexes">
                <div v-for="index in indexes" v-bind:key="index.id" class="main__modal_selected_index"
                    :class="{ml_8: index.id !== 1}"
                >
                    <div class="selected_index__text">
                        кам
                    </div>
                    <svg class="ml_8" width="15" height="16" viewBox="0 0 15 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <rect y="0.5" width="15" height="15" rx="7.5" fill="#E5E7EB" />
                        <path fill-rule="evenodd" clip-rule="evenodd"
                            d="M10.4268 5.07296C10.4501 5.09618 10.4686 5.12377 10.4812 5.15414C10.4938 5.18451 10.5003 5.21707 10.5003 5.24996C10.5003 5.28284 10.4938 5.3154 10.4812 5.34578C10.4686 5.37615 10.4501 5.40374 10.4268 5.42696L4.92683 10.927C4.87988 10.9739 4.81622 11.0003 4.74983 11.0003C4.68344 11.0003 4.61977 10.9739 4.57283 10.927C4.52588 10.88 4.49951 10.8163 4.49951 10.75C4.49951 10.6836 4.52588 10.6199 4.57283 10.573L10.0728 5.07296C10.0961 5.04968 10.1236 5.03121 10.154 5.0186C10.1844 5.006 10.2169 4.99951 10.2498 4.99951C10.2827 4.99951 10.3153 5.006 10.3456 5.0186C10.376 5.03121 10.4036 5.04968 10.4268 5.07296Z"
                            fill="#6B7280" />
                        <path fill-rule="evenodd" clip-rule="evenodd"
                            d="M4.57296 5.07296C4.54968 5.09618 4.53121 5.12377 4.5186 5.15414C4.506 5.18451 4.49951 5.21707 4.49951 5.24996C4.49951 5.28284 4.506 5.3154 4.5186 5.34578C4.53121 5.37615 4.54968 5.40374 4.57296 5.42696L10.073 10.927C10.1199 10.9739 10.1836 11.0003 10.25 11.0003C10.3163 11.0003 10.38 10.9739 10.427 10.927C10.4739 10.88 10.5003 10.8163 10.5003 10.75C10.5003 10.6836 10.4739 10.6199 10.427 10.573L4.92696 5.07296C4.90374 5.04968 4.87615 5.03121 4.84578 5.0186C4.8154 5.006 4.78284 4.99951 4.74996 4.99951C4.71707 4.99951 4.68451 5.006 4.65414 5.0186C4.62377 5.03121 4.59618 5.04968 4.57296 5.07296Z"
                            fill="#6B7280" />
                    </svg>
                </div>
            </div>

            <svg class="ml-14" width="12" height="8" viewBox="0 0 12 8" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd"
                    d="M6.30969 6.93476C6.26905 6.9755 6.22077 7.00783 6.16762 7.02988C6.11446 7.05194 6.05748 7.06329 5.99994 7.06329C5.94239 7.06329 5.88541 7.05194 5.83226 7.02988C5.77911 7.00783 5.73083 6.9755 5.69019 6.93476L0.440187 1.68476C0.358037 1.60261 0.311884 1.49119 0.311884 1.37501C0.311884 1.25883 0.358037 1.14741 0.440187 1.06526C0.522337 0.98311 0.633758 0.936958 0.749938 0.936958C0.866116 0.936958 0.977537 0.98311 1.05969 1.06526L5.99994 6.00639L10.9402 1.06526C11.0223 0.983111 11.1338 0.936959 11.2499 0.936959C11.3661 0.936959 11.4775 0.983111 11.5597 1.06526C11.6418 1.14741 11.688 1.25883 11.688 1.37501C11.688 1.49119 11.6418 1.60261 11.5597 1.68476L6.30969 6.93476Z"
                    fill="#374151" />
            </svg>

            <!-- dd -->
            <drop-down v-show="show_dd_indexes" :items='items' />
        </div>

        <div class="main__modal_label mt-20">Настроить индекс</div>
        <!-- <div class="main__modal_selecter mt-10">
            <div class="text-2">Выбрать индекс</div>

            <svg class="ml-14" width="12" height="8" viewBox="0 0 12 8" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd"
                    d="M6.30969 6.93476C6.26905 6.9755 6.22077 7.00783 6.16762 7.02988C6.11446 7.05194 6.05748 7.06329 5.99994 7.06329C5.94239 7.06329 5.88541 7.05194 5.83226 7.02988C5.77911 7.00783 5.73083 6.9755 5.69019 6.93476L0.440187 1.68476C0.358037 1.60261 0.311884 1.49119 0.311884 1.37501C0.311884 1.25883 0.358037 1.14741 0.440187 1.06526C0.522337 0.98311 0.633758 0.936958 0.749938 0.936958C0.866116 0.936958 0.977537 0.98311 1.05969 1.06526L5.99994 6.00639L10.9402 1.06526C11.0223 0.983111 11.1338 0.936959 11.2499 0.936959C11.3661 0.936959 11.4775 0.983111 11.5597 1.06526C11.6418 1.14741 11.688 1.25883 11.688 1.37501C11.688 1.49119 11.6418 1.60261 11.5597 1.68476L6.30969 6.93476Z"
                    fill="#374151" />
            </svg>
        </div> -->

        <div style="width: 100%; position: relative;">
            <input class="main__modal_input mt-10" placeholder="Выбрать индекс" />

            <svg class="cntr_svg_arrow" width="12" height="8" viewBox="0 0 12 8" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd"
                    d="M6.30969 6.93476C6.26905 6.9755 6.22077 7.00783 6.16762 7.02988C6.11446 7.05194 6.05748 7.06329 5.99994 7.06329C5.94239 7.06329 5.88541 7.05194 5.83226 7.02988C5.77911 7.00783 5.73083 6.9755 5.69019 6.93476L0.440187 1.68476C0.358037 1.60261 0.311884 1.49119 0.311884 1.37501C0.311884 1.25883 0.358037 1.14741 0.440187 1.06526C0.522337 0.98311 0.633758 0.936958 0.749938 0.936958C0.866116 0.936958 0.977537 0.98311 1.05969 1.06526L5.99994 6.00639L10.9402 1.06526C11.0223 0.983111 11.1338 0.936959 11.2499 0.936959C11.3661 0.936959 11.4775 0.983111 11.5597 1.06526C11.6418 1.14741 11.688 1.25883 11.688 1.37501C11.688 1.49119 11.6418 1.60261 11.5597 1.68476L6.30969 6.93476Z"
                    fill="#374151" />
            </svg>
        </div>

        <div class="main__modal_label mt-20">Задать имя</div>
        <div style="width: 100%; position: relative;">
            <input class="main__modal_input mt-10" :class="{bg_success: name_success, bg_wrong: name_wrong}" placeholder="Не выбрано" />

            <svg v-if="name_success" class="cntr_svg_arrow" width="11" height="10" viewBox="0 0 11 10" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M9.73598 0.969934C9.80423 0.9003 9.88568 0.844981 9.97557 0.807217C10.0655 0.769452 10.162 0.75 10.2595 0.75C10.357 0.75 10.4535 0.769452 10.5434 0.807217C10.6333 0.844981 10.7147 0.9003 10.783 0.969934C11.069 1.25893 11.073 1.72593 10.793 2.01993L4.87998 9.00993C4.81285 9.08366 4.73138 9.1429 4.64056 9.18406C4.54974 9.22521 4.45148 9.2474 4.35179 9.24927C4.2521 9.25115 4.15307 9.23266 4.06077 9.19495C3.96847 9.15723 3.88483 9.10108 3.81498 9.02993L0.21698 5.38393C0.0782173 5.24242 0.000488281 5.05213 0.000488281 4.85393C0.000488281 4.65574 0.0782173 4.46545 0.21698 4.32393C0.285226 4.2543 0.366679 4.19898 0.456569 4.16122C0.546459 4.12345 0.64298 4.104 0.74048 4.104C0.837981 4.104 0.934502 4.12345 1.02439 4.16122C1.11428 4.19898 1.19573 4.2543 1.26398 4.32393L4.31598 7.41693L9.71598 0.991934C9.7222 0.984206 9.72888 0.976859 9.73598 0.969934Z" fill="#3B82F6"/>
            </svg>

        </div>

        <div v-show="name_wrong" class="message_wrong">Данное имя индекса уже занято, попробуйте другое</div>


        <div class="cntr_row mt-65">
            <div class="modal__text_fantom">Фантомная статистика</div>

            <!-- i - info -->
            <div class="cur_p" style="position: relative;" @mouseenter="show_hint = true" @mouseleave="show_hint = false">
                <svg class="ml_8" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" clip-rule="evenodd"
                        d="M3.05025 12.9497C4.36301 14.2625 6.14348 15 8 15C9.85652 15 11.637 14.2625 12.9497 12.9497C14.2625 11.637 15 9.85652 15 8C15 6.14348 14.2625 4.36301 12.9497 3.05025C11.637 1.7375 9.85652 1 8 1C6.14348 1 4.36301 1.7375 3.05025 3.05025C1.7375 4.36301 1 6.14348 1 8C1 9.85652 1.7375 11.637 3.05025 12.9497ZM13.6569 13.6569C12.1566 15.1571 10.1217 16 8 16C5.87827 16 3.84344 15.1571 2.34315 13.6569C0.842855 12.1566 0 10.1217 0 8C0 5.87827 0.842855 3.84344 2.34315 2.34315C3.84344 0.842855 5.87827 0 8 0C10.1217 0 12.1566 0.842855 13.6569 2.34315C15.1571 3.84344 16 5.87827 16 8C16 10.1217 15.1571 12.1566 13.6569 13.6569ZM6.63995 6.875L8.92995 6.588L7.92895 11.293C7.85795 11.633 7.95795 11.826 8.23295 11.826C8.42695 11.826 8.71895 11.756 8.91895 11.58L8.83095 11.996C8.54395 12.342 7.91095 12.594 7.36595 12.594C6.66295 12.594 6.36395 12.172 6.55795 11.275L7.29595 7.807C7.35995 7.514 7.30195 7.408 7.00795 7.338L6.55795 7.255L6.63995 6.875ZM8.70706 5.20711C8.8946 5.01957 8.99995 4.76522 8.99995 4.5C8.99995 4.23478 8.8946 3.98043 8.70706 3.79289C8.51952 3.60536 8.26517 3.5 7.99995 3.5C7.73474 3.5 7.48038 3.60536 7.29285 3.79289C7.10531 3.98043 6.99995 4.23478 6.99995 4.5C6.99995 4.76522 7.10531 5.01957 7.29285 5.20711C7.48038 5.39464 7.73474 5.5 7.99995 5.5C8.26517 5.5 8.51952 5.39464 8.70706 5.20711Z"
                        fill="#6B7280" />
                </svg>
                <hint-black v-show="show_hint" />
            </div>


            <!-- switch -->
            <div @click="swith_on = !swith_on" class="ml_8" :class="{main__modal_fantom_cntr_icon: !swith_on, main__modal_fantom_cntr_icon_on: swith_on}">
                <svg v-show="!swith_on" width="28" height="27" viewBox="0 0 28 27" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <g filter="url(#filter0_dd_409_62113)">
                        <rect x="2" y="1" width="24" height="24" rx="12" fill="white" shape-rendering="crispEdges" />
                        <path fill-rule="evenodd" clip-rule="evenodd"
                            d="M17.6587 9.34132C17.6878 9.37035 17.7108 9.40483 17.7266 9.4428C17.7424 9.48077 17.7505 9.52147 17.7505 9.56257C17.7505 9.60367 17.7424 9.64438 17.7266 9.68234C17.7108 9.72031 17.6878 9.75479 17.6587 9.78382L10.7837 16.6588C10.725 16.7175 10.6454 16.7505 10.5624 16.7505C10.4794 16.7505 10.3998 16.7175 10.3412 16.6588C10.2825 16.6001 10.2495 16.5206 10.2495 16.4376C10.2495 16.3546 10.2825 16.275 10.3412 16.2163L17.2162 9.34132C17.2452 9.31222 17.2797 9.28913 17.3176 9.27338C17.3556 9.25762 17.3963 9.24951 17.4374 9.24951C17.4785 9.24951 17.5192 9.25762 17.5572 9.27338C17.5951 9.28913 17.6296 9.31222 17.6587 9.34132Z"
                            fill="#6B7280" />
                        <path fill-rule="evenodd" clip-rule="evenodd"
                            d="M10.3413 9.34132C10.3122 9.37035 10.2891 9.40483 10.2734 9.4428C10.2576 9.48077 10.2495 9.52147 10.2495 9.56257C10.2495 9.60367 10.2576 9.64438 10.2734 9.68234C10.2891 9.72031 10.3122 9.75479 10.3413 9.78382L17.2163 16.6588C17.275 16.7175 17.3546 16.7505 17.4376 16.7505C17.5206 16.7505 17.6001 16.7175 17.6588 16.6588C17.7175 16.6001 17.7505 16.5206 17.7505 16.4376C17.7505 16.3546 17.7175 16.275 17.6588 16.2163L10.7838 9.34132C10.7548 9.31222 10.7203 9.28913 10.6823 9.27338C10.6444 9.25762 10.6037 9.24951 10.5626 9.24951C10.5215 9.24951 10.4808 9.25762 10.4428 9.27338C10.4048 9.28913 10.3703 9.31222 10.3413 9.34132Z"
                            fill="#6B7280" />
                    </g>
                    <defs>
                        <filter id="filter0_dd_409_62113" x="0" y="0" width="28" height="28" filterUnits="userSpaceOnUse"
                            color-interpolation-filters="sRGB">
                            <feFlood flood-opacity="0" result="BackgroundImageFix" />
                            <feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0"
                                result="hardAlpha" />
                            <feOffset dy="1" />
                            <feGaussianBlur stdDeviation="0.5" />
                            <feComposite in2="hardAlpha" operator="out" />
                            <feColorMatrix type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.06 0" />
                            <feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow_409_62113" />
                            <feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0"
                                result="hardAlpha" />
                            <feOffset dy="1" />
                            <feGaussianBlur stdDeviation="1" />
                            <feComposite in2="hardAlpha" operator="out" />
                            <feColorMatrix type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.1 0" />
                            <feBlend mode="normal" in2="effect1_dropShadow_409_62113"
                                result="effect2_dropShadow_409_62113" />
                            <feBlend mode="normal" in="SourceGraphic" in2="effect2_dropShadow_409_62113" result="shape" />
                        </filter>
                    </defs>
                </svg>
                <svg v-show="!swith_on" width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M14.9602 9.48121C15.0028 9.43769 15.0537 9.40311 15.1099 9.37951C15.1661 9.35591 15.2264 9.34375 15.2874 9.34375C15.3483 9.34375 15.4086 9.35591 15.4648 9.37951C15.521 9.40311 15.5719 9.43769 15.6145 9.48121C15.7933 9.66183 15.7958 9.95371 15.6208 10.1375L11.9252 14.5062C11.8832 14.5523 11.8323 14.5893 11.7755 14.615C11.7188 14.6408 11.6574 14.6546 11.595 14.6558C11.5327 14.657 11.4709 14.6454 11.4132 14.6218C11.3555 14.5983 11.3032 14.5632 11.2595 14.5187L9.0108 12.24C8.92407 12.1515 8.87549 12.0326 8.87549 11.9087C8.87549 11.7848 8.92407 11.6659 9.0108 11.5775C9.05345 11.5339 9.10436 11.4994 9.16054 11.4758C9.21672 11.4522 9.27705 11.44 9.33798 11.44C9.39892 11.44 9.45925 11.4522 9.51543 11.4758C9.57161 11.4994 9.62252 11.5339 9.66517 11.5775L11.5727 13.5106L14.9477 9.49496C14.9516 9.49013 14.9557 9.48554 14.9602 9.48121Z"
                        fill="#6B7280" />
                </svg>

                <svg v-show="swith_on" class="svg_switch_cross_on" width="10" height="10" viewBox="0 0 10 10" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" clip-rule="evenodd" d="M8.65866 1.34132C8.68776 1.37035 8.71085 1.40483 8.7266 1.4428C8.74236 1.48077 8.75046 1.52147 8.75046 1.56257C8.75046 1.60367 8.74236 1.64438 8.7266 1.68234C8.71085 1.72031 8.68776 1.75479 8.65866 1.78382L1.78366 8.65882C1.72498 8.7175 1.64539 8.75047 1.56241 8.75047C1.47942 8.75047 1.39984 8.7175 1.34116 8.65882C1.28248 8.60014 1.24951 8.52056 1.24951 8.43757C1.24951 8.35459 1.28248 8.275 1.34116 8.21632L8.21616 1.34132C8.24518 1.31222 8.27967 1.28913 8.31764 1.27338C8.3556 1.25762 8.3963 1.24951 8.43741 1.24951C8.47851 1.24951 8.51921 1.25762 8.55718 1.27338C8.59514 1.28913 8.62963 1.31222 8.65866 1.34132Z" fill="white"/>
                    <path fill-rule="evenodd" clip-rule="evenodd" d="M1.34132 1.34132C1.31222 1.37035 1.28913 1.40483 1.27338 1.4428C1.25762 1.48077 1.24951 1.52147 1.24951 1.56257C1.24951 1.60367 1.25762 1.64438 1.27338 1.68234C1.28913 1.72031 1.31222 1.75479 1.34132 1.78382L8.21632 8.65882C8.275 8.7175 8.35459 8.75047 8.43757 8.75047C8.52056 8.75047 8.60014 8.7175 8.65882 8.65882C8.7175 8.60014 8.75047 8.52056 8.75047 8.43757C8.75047 8.35459 8.7175 8.275 8.65882 8.21632L1.78382 1.34132C1.75479 1.31222 1.72031 1.28913 1.68234 1.27338C1.64438 1.25762 1.60367 1.24951 1.56257 1.24951C1.52147 1.24951 1.48077 1.25762 1.4428 1.27338C1.40483 1.28913 1.37035 1.31222 1.34132 1.34132Z" fill="white"/>
                </svg>

                <svg v-show="swith_on" class="svg_switch_check_on" width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <rect width="24" height="24" rx="12" fill="white"/>
                    <path d="M14.9602 9.48121C15.0028 9.43769 15.0537 9.40311 15.1099 9.37951C15.1661 9.35591 15.2264 9.34375 15.2874 9.34375C15.3483 9.34375 15.4086 9.35591 15.4648 9.37951C15.521 9.40311 15.5719 9.43769 15.6145 9.48121C15.7933 9.66183 15.7958 9.95371 15.6208 10.1375L11.9252 14.5062C11.8832 14.5523 11.8323 14.5893 11.7755 14.615C11.7188 14.6408 11.6574 14.6546 11.595 14.6558C11.5327 14.657 11.4709 14.6454 11.4132 14.6218C11.3555 14.5983 11.3032 14.5632 11.2595 14.5187L9.0108 12.24C8.92407 12.1515 8.87549 12.0326 8.87549 11.9087C8.87549 11.7848 8.92407 11.6659 9.0108 11.5775C9.05345 11.5339 9.10436 11.4994 9.16054 11.4758C9.21672 11.4522 9.27705 11.44 9.33798 11.44C9.39892 11.44 9.45925 11.4522 9.51543 11.4758C9.57161 11.4994 9.62252 11.5339 9.66517 11.5775L11.5727 13.5106L14.9477 9.49496C14.9516 9.49013 14.9557 9.48554 14.9602 9.48121Z" fill="#3B82F6"/>
                </svg>



                
            </div>
        </div>

        <div class="main__modal_futter">
            <div class="main__modal_btn_cancel">Отмена</div>
            <div class="main__modal_btn_add">Добавить аккаунт</div>
        </div>

    </div>
</template>

<script>
import HintBlack from './HintBlack.vue'
import DropDown from './DropDown.vue'
// import SvgCancel from './svg/SvgCancel.vue'
// import SvgStop from './svg/SvgStop.vue'
// import SvgAttention from './svg/SvgAttention.vue'

export default {
    data() {
        return {
            name_success: true,
            name_wrong: false,
            show_hint: false,
            show_dd_indexes: false,
            swith_on: true,
            items: [
                { id: 1, text: 'кам', hover: true },
                { id: 2, text: 'сам', hover: false },
                { id: 3, text: 'сам', hover: false },
                { id: 4, text: 'сам', hover: false },
                { id: 5, text: 'сам', hover: false },
            ],
            indexes: [
                {id: 1, text: 'кам'},
                {id: 2, text: 'сам'},
                {id: 3, text: 'кам'},
            ]
        }
    },
    components: {
        'hint-black': HintBlack,
        'drop-down': DropDown,
    }
}

</script>

<style scoped>
.bg_success {
    background: #F2F7FF;
}
.bg_wrong {
    background: #FFFFFF;
    border: 1px solid #F87171;
    /* Drop Shadow/sm */

    box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.05);

    color: #F87171
}
.cntr_svg_arrow {
    position: absolute;
    right: 16px;
    top: calc(50% - 4px);
}
.main__modal_cntr_selected_indexes {
    display:flex;
    justify-content: left;
    align-items: center;
}
.selected_index__text {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 12px;
    line-height: 16px;
    /* identical to box height, or 133% */

    letter-spacing: 0.005em;

    /* Gray/500 */

    color: #6B7280;
}

.main__modal_selected_index {
    display: flex;
    flex-direction: row;
    align-items: center;
    padding: 6px;
    gap: 1px;

    /* width: 59px; */
    height: 16px;

    /* Gray/200 */

    border: 1px solid #E5E7EB;
    border-radius: 999px;
}

.cur_p {
    cursor: pointer;
}

.ml_8 {
    margin-left: 8px;
}

.mt-65 {
    margin-top: 65px;
}

.mt-20 {
    margin-top: 20px;
}

.mt-10 {
    margin-top: 10px;
}

.line {
    /* width: 1050px; */
    height: 1px;

    background: #E5E7EB;
}

.main__modal_btn_add {
    margin-right: 20px;
    margin-left: 10px;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    padding: 10px 12px;
    gap: 8px;

    height: 18px;

    /* Blue/500 */

    background: #3B82F6;
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
}

.main__modal_btn_cancel {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    padding: 10px 12px;
    gap: 8px;

    /* White/White */

    background: #FFFFFF;
    /* Gray/200 */

    border: 1px solid #E5E7EB;
    /* Drop Shadow/sm */

    box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.05);
    border-radius: 6px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 15px;
    line-height: 18px;
    text-align: center;
    letter-spacing: 0.005em;

    height: 18px;

    color: #1F2937;

}

.main__modal_futter {
    margin-top: 35px;
    margin-left: -3vw;
    margin-bottom: -3vw;
    display: flex;
    justify-content: right;
    align-items: center;
    height: 78px;

    /* Gray/50 */

    background: #F9FAFB;
    /* Gray/200 */

    border-top: 1px solid #E5E7EB;
    width: calc(100% + 6vw);
}

.main__modal_fantom_cntr_icon {
    cursor: pointer;
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    padding: 1px;

    /* Gray/100 */

    background: #F3F4F6;
    border-radius: 999px;
}

.main__modal_fantom_cntr_icon_on {
    cursor: pointer;
    display: flex;
    flex-direction: row;
    align-items: center;
    padding: 2.5px;

    /* Gray/100 */

    background: #3B82F6;
    border-radius: 999px;
}

.svg_switch_check_on {
    margin-left: 6.25px;
}

.svg_switch_cross_on {
    margin-left: 7.25px;
}

.cntr_row {
    display: flex;
    align-items: center;
}

.main__modal {
    width: 33vw;
    position: absolute;
    top: calc(50% - 20vw);
    left: calc(50% - 20vw);

    padding: 3vw;

    background: #FFFFFF;
    /* Drop Shadow/xl */

    box-shadow: 0px 20px 13px rgba(0, 0, 0, 0.03), 0px 8px 5px rgba(0, 0, 0, 0.08);
    border-radius: 16px;
}

.main__modal_title {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 20px;
    line-height: 24px;
    letter-spacing: 0.005em;

    color: #000000;

    text-align: left;
}

.main__modal_label {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 14px;
    line-height: 17px;
    /* identical to box height */

    letter-spacing: 0.005em;

    /* Gray/800 */

    color: #1F2937;

    text-align: left;
}

.main__modal_selecter {
    border: 1px solid #E5E7EB;
    /* Drop Shadow/sm */

    box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.05);
    border-radius: 6px;

    display: flex;
    align-items: center;
    justify-content: space-between;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 15px;
    line-height: 18px;
    letter-spacing: 0.005em;

    /* Gray/500 */

    color: #6B7280;
    padding: 0px 16px 0px 16px;
    height: 44px;
    position: relative;
}

.main__modal_input {
    border: 1px solid #E5E7EB;
    /* Drop Shadow/sm */

    box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.05);
    border-radius: 6px;

    display: flex;
    align-items: center;
    justify-content: space-between;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 15px;
    line-height: 18px;
    letter-spacing: 0.005em;

    width: calc(100% - 32px);
    /* Gray/500 */

    /* color: #6B7280; */
    padding: 14px 16px 14px 16px;
}

.bg_wrong:focus {
    border: 1px solid #F87171;
    outline: none;
}

.message_wrong {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 17px;
    /* identical to box height */

    letter-spacing: 0.005em;

    color: #F87171;

    text-align: left;

    margin-top: 10px;
}

.modal__text_fantom {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 400;
    font-size: 13.0612px;
    line-height: 16px;
    /* identical to box height */

    letter-spacing: 0.005em;

    color: #6B7280;
}
</style>