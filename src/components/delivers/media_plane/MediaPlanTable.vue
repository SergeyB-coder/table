<template>
    <div v-show="showMediaPlan" style="overflow-x: scroll; height: 100%;">
        <table class="media_plan_table">
            <!-- Заголовки -->
            <tr class="header">
                <th v-for="header in headers" :key="header.text" :style="{ width: header.width }">
                    {{ header.text }}
                </th>
            </tr>
            <!-- Строки -->
            <tr v-for="row in rows" :key="row.id" >
                <td class="table_mediaplane_text" :class="{ td_input: out_project_mode, border_red: is_wrong_data }" >
                    <div v-show="out_project_mode" class="cntr_input_new_line">
                        <input class="input_new_line text-2 w-100" />
                    </div>

                    <div v-show="!out_project_mode">
                        {{ row.index }}
                        <svg @click="show_index = !show_index" @mouseleave="input_bg_active = false"
                            @mouseenter="input_bg_active = true" class="input__svg_arrow"
                            :class="{ rotate_180: show_index }" width="16" height="16" viewBox="0 0 16 16" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                                fill="#6B7280" />
                        </svg>
                    </div>
                    <SelecterItem v-show="show_index" :width="'283px'" :align="'left'"
                        :items="['Индекс 1', 'Индекс 2', '+ Внешний проект']"
                        @change-mode="out_project_mode = true; show_index = false" />
                </td>
                <td :class="{ border_red: is_wrong_data }">
                    <label class="table_mediaplane_text">{{ row.line }}</label>
                    <svg @click="show_line = !show_line" @mouseleave="input_bg_active = false"
                        @mouseenter="input_bg_active = true" class="input__svg_arrow" :class="{ rotate_180: show_line }"
                        width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path fill-rule="evenodd" clip-rule="evenodd"
                            d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                            fill="#6B7280" />
                    </svg>
                    <SelecterItem v-show="show_line" :width="'283px'" :items="['Все', 'Линия 1', 'Линия 2']" />
                </td>
                <td style="cursor: pointer;" @click="show_input_views_day = true"
                    :class="{ td_input: show_input_views_day, border_red: is_wrong_data }">
                    <label v-show="!show_input_views_day" class="table_mediaplane_text">{{ row.views_day }}</label>
                    <div v-show="show_input_views_day" class="cntr_input_new_line">
                        <input class="input_new_line text-2 w-100" />
                    </div>
                </td>
                <td style="cursor: pointer;" @click="show_input_views_month = true"
                    :class="{ td_input: show_input_views_month, border_red: is_wrong_data }">
                    <label v-show="!show_input_views_month" class="table_mediaplane_text">{{ row.views_month }}</label>
                    <div v-show="show_input_views_month" class="cntr_input_new_line">
                        <input class="input_new_line text-2 w-100" />
                    </div>
                </td>
                <td style="cursor: pointer;" @click="show_input_ctr = true" :class="{ td_input: show_input_ctr, border_red: is_wrong_data }">
                    <label v-show="!show_input_ctr" class="table_mediaplane_text">{{ row.ctr }}</label>
                    <div v-show="show_input_ctr" class="cntr_input_new_line">
                        <input class="input_new_line text-2 w-100" />
                    </div>
                </td>

            </tr>

            <tr>
                <td class="table_mediaplane_text" :class="{ td_input: out_project_mode }" colspan="2">
                    <div v-show="out_project_mode" class="cntr_input_new_line">
                        <input class="input_new_line text-2 w-100" />
                    </div>

                    <div v-show="!out_project_mode">
                        Итог
                    </div>
                </td>
                <td>
                </td>
                <td>
                </td>
                <td>
                </td>

            </tr>
        </table>
    </div>
</template>

<script>
import SelecterItem from './SelecterItem.vue';

export default {
    name: "MediaPlanTable",
    data() {
        return {
            show_index: false,
            show_line: false,
            out_project_mode: false,
            show_input_views_day: false,
            show_input_views_month: false,
            show_input_ctr: false,
            is_wrong_data: false,
        }
    },
    components: {
        SelecterItem,
    },
    props: {
        showMediaPlan: {
            type: Boolean,
            required: true,
        },
        headers: {
            type: Array,
            required: true,
        },
        rows: {
            type: Array,
            required: true,
        },
    },
};
</script>

<style scoped>
.border_red {
    border: 1px solid #F87171;
    border-right-width: 0
}
.border_red:last-child {
    border-right-width: 1px; 
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

.td_input {
    background: #F3F4F6;
}

.cntr_input_new_line {
    display: flex;
    align-items: center;
}

.input_new_line {
    outline: none;
    border: none;
    background: #F3F4F6;
}

.rotate_180 {
    transform: rotate(180deg) translateY(50%) !important;
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

table {
    margin-top: 18px;
    /* border-collapse: collapse; */
    border-spacing: 0;
    /* width: 107vw; */
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

td {
    text-align: left;
    padding-left: 20px;
    border: 1px solid var(--gray-200, #E5E7EB);
    position: relative;
    height: 44px;


}

.input__svg_arrow {
    position: absolute;
    right: 20px;
    top: 50%;
    transform: translateY(-50%);
    cursor: pointer;
}

.table_mediaplane_text {
    color: var(--gray-800, #1F2937);
    font-family: Inter;
    font-size: 14px;
    font-style: normal;
    font-weight: 500;
    line-height: 20px;
}

th {
    border: 1px solid var(--gray-200, #E5E7EB);
    position: relative;
    height: 44px;
    cursor: pointer
}

.media_plan_table {
    width: max-content !important;
}

.header {
    position: sticky;
    top: 0px;
    background-color: #fff;
    z-index: 11;
    border: 1px solid var(--gray-200, #E5E7EB);
}

.w-100 {
    width: 100%;
}
</style>