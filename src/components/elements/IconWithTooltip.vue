<template>
    <div class="tooltip-container" @mouseenter="showTooltip" @mouseleave="hideTooltip">
        <svg-caution v-show="iconType === 'caution'" />
        <svg-greenlightning v-show="iconType === 'greenlightning'" />
        <svg-greenpause v-show="iconType === 'greenpause'" />
        <svg-redpause v-show="iconType === 'redpause'" />
        <svg-redplay v-show="iconType === 'redplay'" />
        <div class="tooltip" v-if="isTooltipVisible">
            {{ tooltipText }}
        </div>
    </div>
</template>

<script>
import SvgCaution from '../svg/SvgCaution.vue'
import SvgGreenLightning from '../svg/SvgGreenLightning.vue'
import SvgGreenPause from '../svg/SvgGreenPause.vue'
import SvgRedPause from '../svg/SvgRedPause.vue'
import SvgRedPlay from '../svg/SvgRedPlay.vue'


export default {
    props: {
        iconType: {
            type: String,
            required: true
        },
        tooltipText: {
            type: String,
            required: true
        }
    },
    data() {
        return {
            isTooltipVisible: false
        };
    },
    components: {
        'svg-caution': SvgCaution,
        'svg-greenlightning': SvgGreenLightning,
        'svg-greenpause': SvgGreenPause,
        'svg-redpause': SvgRedPause,
        'svg-redplay': SvgRedPlay
    },
    methods: {
        showTooltip() {
            this.isTooltipVisible = true;
        },
        hideTooltip() {
            this.isTooltipVisible = false;
        }
    }
};
</script>

<style scoped>
.tooltip-container {
    position: relative;
    display: inline-block;
}

.tooltip {
    position: absolute;
    right: -116px;
    top: -48px;
    background-color: #3B82F6;
    color: white;
    font-family: Inter;
    font-size: 12px;
    font-weight: 500;
    line-height: 16px;
    letter-spacing: 0.005em;
    text-align: center;
    width: 92px;
    padding: 16px 12px;
    border-radius: 8px;
    opacity: 1;
    z-index: 12;
    box-shadow: 0px 14px 11px 0px #0000001A;
}
</style>