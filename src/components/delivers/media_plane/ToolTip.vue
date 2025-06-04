<template>
  <div class="centered-box" :style="{ width: dynamicWidth }">
    {{ text }}
  </div>
</template>

<script>
export default {
  name: "CenteredBox",
  props: {
    text: {
      type: String,
      required: true,
    },
    width: {
      type: [String, Number], // Поддержка чисел и строк
      default: '101px', // Значение по умолчанию
    },
  },
  computed: {
    dynamicWidth() {
      // Преобразуем числовое значение в строку с 'px', если передано число
      return typeof this.width === 'number' ? `${this.width}px` : this.width;
    },
  },
};
</script>

<style scoped>
.centered-box {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 48px;
  background-color: #3B82F6;
  border-radius: 8px;
  color: white;

  position: absolute;
  bottom: 75%;
  left: 55%;
  z-index: 1000;

  font-family: Inter;
  font-size: 12px;
  font-style: normal;
  font-weight: 500;
}
</style>
