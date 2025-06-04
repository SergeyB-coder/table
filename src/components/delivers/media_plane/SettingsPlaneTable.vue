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

            </tr>
        </table>
        <div class="cntr_message_delete">
            <SvgLike/>
            Медиаплан “Новый медиаплан 1” успешно удален
        </div>
    </div>
</template>

<script>
import SvgLike from './SvgLike.vue';


export default {
    name: "SettingsPlaneTable",
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
        SvgLike
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
.cntr_message_delete {
    border: 1px solid #F87171;
    border-radius: 8px;
    position: absolute; 
    bottom: 0; 
    right: 50px; 
    display: flex;
    width: 276px;
    padding: 12px 18px;
}
.message_text {
    color: var(--gray-800, #6B7280);
    font-family: Inter;
    font-size: 13px;
    font-style: normal;
    font-weight: 400;
    line-height: 16px;
}

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