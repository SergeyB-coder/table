<template>
    <div style="overflow-x: scroll; height: 100%;">
        <table class="media_plan_table">
            <!-- Заголовки -->
            <tr class="header">
                <th style=" width: 120px; vertical-align: bottom; padding-bottom: 15px;" rowspan="2">
                    Индекс
                </th>
                <th style=" width: 120px; vertical-align: bottom; padding-bottom: 15px;" rowspan="2">
                    Линия
                </th>
                <th style=" width: 120px; text-align: center" colspan="4">
                    Расчетные данные
                </th>
                <th style=" width: 120px; text-align: center" colspan="4">
                    Полученые данные
                </th>
                <th style=" width: 120px; text-align: center" colspan="3">
                    Доля выполнения плана
                </th>
            </tr>
            <tr class="header">
                <th style=" width: 201px" >
                    КПЭ показы (день), расчет
                </th>
                <th style=" width: 201px" >
                    КПЭ показы (месяц), расчет
                </th>
                <th style=" width: 201px" >
                    КПЭ CTR,%   
                </th>
                <th style=" width: 201px" >
                    Бюджет итоговый, руб
                </th>
                <th style=" width: 201px" >
                    Показы (месяц)
                </th>
                <th style=" width: 201px" >
                    КПЭ CTR, %
                </th>
                <th style=" width: 201px" >
                    Бюджет итоговый, руб
                </th>
                <th style=" width: 201px" >
                    Показы (день), полученные
                </th>
                <th style=" width: 201px" >
                    Показы (месяц), полученные
                </th>
                <th style=" width: 201px" >
                    Бюджет итоговый, руб
                </th>
                
                <th style=" width: 201px" >
                    Бюджет итоговый, руб
                </th>
            </tr>
            <!-- Строки -->
            <tr v-for="row in rows" :key="row.id" >
                <td class="table_mediaplane_text"  >
                    <div v-show="!out_project_mode">
                        {{ row.index }}
                    </div>
                </td>
                <td :class="{ border_red: is_wrong_data }">
                    <label class="table_mediaplane_text">{{ row.line }}</label>
                    
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
                <td style="cursor: pointer;" >
                    <label v-show="!show_input_ctr" class="table_mediaplane_text">{{ row.ctr }}</label>
                </td>
                <td style="cursor: pointer;" >
                    <label v-show="!show_input_ctr" class="table_mediaplane_text">{{ row.ctr2 }}</label>
                </td>
                <td style="cursor: pointer;" >
                    <label v-show="!show_input_ctr" class="table_mediaplane_text">{{ row.dev }}</label>
                </td>
                <td style="cursor: pointer;" >
                    <label v-show="!show_input_ctr" class="table_mediaplane_text">{{ row.dev }}</label>
                </td>
                <td style="cursor: pointer;" >
                    <label v-show="!show_input_ctr" class="table_mediaplane_text">{{ row.col8 }}</label>
                </td>
                <td style="cursor: pointer;" >
                    <label v-show="!show_input_ctr" class="table_mediaplane_text">{{ row.col9 }}</label>
                </td>
                <td style="cursor: pointer;" >
                    <label v-show="!show_input_ctr" class="table_mediaplane_text">{{ row.col10 }}</label>
                </td>
                <td style="cursor: pointer;" >
                    <label v-show="!show_input_ctr" class="table_mediaplane_text">{{ row.col11 }}</label>
                </td>
                <td style="cursor: pointer;" >
                    <label v-show="!show_input_ctr" class="table_mediaplane_text">{{ row.col12 }}</label>
                </td>

            </tr>

            <tr >
                <td class="table_mediaplane_text"  colspan="2">

                    <div style="font-weight: 700 !important;" v-show="!out_project_mode">
                        Итог
                    </div>
                </td>
                <td>
                </td>
                <td>
                </td>
                <td>
                </td>
                <td>
                </td>
                <td>
                </td>
                <td>
                </td>
                <td>
                </td>
                <td>
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
// import SelecterItem from './SelecterItem.vue';

export default {
    name: "ShowPlaneTable",
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
    },
    props: {
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

tr:nth-child(-n+2) th {
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