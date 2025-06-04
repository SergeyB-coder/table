<template>
    <div class="wrap-selecter-item" :style="{ width: width }" :class="{left_align: align === 'left', right_align: align === 'right'}">
      <div class="selecter-item-container">
        <div
          v-for="(item, index) in items"
          :key="item"
          class="selecter-item box-select"
          @click="index === items.length - 1 ? handleItemClick() : null"
        >
          <div class="text-2 color-1 ml-8">{{ item }}</div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "SelecterItem",
    props: {
      items: {
        type: Array,
        required: true,
      },
      width: {
        type: String,
        default: "100%", // Значение по умолчанию
      },
      align: {
        type: String,
        default: "right", // Значение по умолчанию
      },
    },
    methods: {
    handleItemClick() {
      this.$emit("change-mode"); // Отправляем событие вверх
    },
  },
  };
  </script>
  
  <style scoped>
  .text-2 {
    font-family: "Inter";
    font-style: normal;
    font-weight: 500;
    font-size: 12px;
    line-height: 16px;
    letter-spacing: 0.005em;
    text-align: left;
  }
  
  .color-1 {
    color: #6b7280;
  }
  
  .color-2 {
    color: #3b82f6;
  }
  
  ::-webkit-scrollbar {
    width: 6px;
    margin-right: 5px;
  }
  
  /* Handle */
  ::-webkit-scrollbar-thumb {
    border-radius: 10px;
    background: #e5e7eb;
  }
  
  .selecter-item-container {
    box-sizing: border-box;
    overflow: scroll;
    overflow-x: hidden;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 0px 0px 8px;
    z-index: 14;
    /* background-color: #3b82f6; */
    width: 100%;
  }
  
  .wrap-selecter-item {
    box-sizing: border-box;
    overflow-x: hidden;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    position: absolute;
    top: 50px;
    background: #ffffff;
    border: 1px solid #e5e7eb;
    box-shadow: 0px 10px 8px rgba(0, 0, 0, 0.04),
      0px 4px 3px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
    z-index: 14;
  }

  .left_align {
    left: 0;
  }

  .right_align {
    right: 0;
  }
  
  .selecter-item {
    padding: 8px 12px;
    margin-left: 8px;
    margin-top: 8px;
    display: flex;
    justify-content: left;
    align-items: center;
    height: 32px;
    cursor: pointer;
    width: 97%;
    box-sizing: border-box;
  }
  
  .selecter-item:hover {
    background: #f2f7ff;
    border-radius: 6px;
  }
  
  .ml-8 {
    margin-left: 8px;
  }
  </style>
  