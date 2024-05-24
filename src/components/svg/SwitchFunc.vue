<template>
    <div class="cntr_switch" :class="{ 'cntr_switch_active': isActive }" @click="toggleSwitch" >
        <div class="thumb_switch" :class="{ 'thumb_switch_active': isActive }">
            

            <svg v-if="isActive" width="20" height="21" viewBox="0 0 20 21" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                    d="M8.81621 13.2639C8.64954 13.2639 8.49121 13.1973 8.37454 13.0806L6.01621 10.7223C5.77454 10.4806 5.77454 10.0806 6.01621 9.83893C6.25788 9.59727 6.65788 9.59727 6.89954 9.83893L8.81621 11.7556L13.0995 7.47227C13.3412 7.2306 13.7412 7.2306 13.9829 7.47227C14.2245 7.71393 14.2245 8.11393 13.9829 8.3556L9.25788 13.0806C9.14121 13.1973 8.98288 13.2639 8.81621 13.2639Z"
                    fill="#3B82F6" />
            </svg>

            <svg v-else width="20" height="21" viewBox="0 0 20 21" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                    d="M7.64172 13.3435C7.48338 13.3435 7.32505 13.2852 7.20005 13.1602C6.95838 12.9185 6.95838 12.5185 7.20005 12.2768L11.9167 7.56016C12.1584 7.31849 12.5584 7.31849 12.8 7.56016C13.0417 7.80182 13.0417 8.20182 12.8 8.44349L8.08338 13.1602C7.96671 13.2852 7.80005 13.3435 7.64172 13.3435Z"
                    fill="white" />
                <path
                    d="M12.3584 13.3435C12.2 13.3435 12.0417 13.2852 11.9167 13.1602L7.20005 8.44349C6.95838 8.20182 6.95838 7.80182 7.20005 7.56016C7.44172 7.31849 7.84172 7.31849 8.08338 7.56016L12.8 12.2768C13.0417 12.5185 13.0417 12.9185 12.8 13.1602C12.675 13.2852 12.5167 13.3435 12.3584 13.3435Z"
                    fill="white" />
            </svg>

        </div>
    </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: false // начальное состояние переключателя
    };
  },
  methods: {
    toggleSwitch() {
      this.isActive = !this.isActive; // переключаем состояние
    }
  }
};
</script>

<style scoped>
.cntr_switch {
    background-color: rgba(59, 130, 246, 0.15);
    width: 57px;
    height: 21px;
    border-radius: 38px;
    display: flex;
    align-items: center;
}

.cntr_switch_active {
    background-color: #3B82F6 !important;
    justify-content: flex-end;
}

.thumb_switch {
    margin-left: 5px;
    background-color: #3B82F6;
    width: 24px;
    height: 17px;
    border-radius: 38px;
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: 0px 0.76px 1.52px 0px #00000066;
    border: 1px solid #fff;


    /* z-index: 10; */
}
.thumb_switch_active {
    background-color: #e6edf9 !important;
    border: 1px solid #86A5DE;
}
</style>