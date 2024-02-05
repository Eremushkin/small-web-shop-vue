<!-- FullBoxComponent.vue -->

<template>
  <div class="full-box" :style="{ width: boxWidth + 'px', height: boxHeight + 'px' }">
    <p>Ширина: {{ boxWidth }}px</p>
    <p>Высота: {{ boxHeight }}px</p>
  </div>
</template>

<script>
export default {
  name: 'FullBoxComponent',
  data() {
    return {
      boxWidth: 0,
      boxHeight: 0,
    };
  },
  mounted() {
    this.updateBoxSize();
    window.addEventListener('resize', this.updateBoxSize);
  },
  // beforeDestroy() {
  //   window.removeEventListener('resize', this.updateBoxSize);
  // },
  methods: {
    updateBoxSize() {
      this.boxWidth = this.$el.offsetWidth;
      this.boxHeight = this.$el.offsetHeight;
    },
  },
};
</script>

<style scoped>
.full-box {
  width: 100%;
  height: 100vh;
  border: 1px solid #ccc;
  box-sizing: border-box;
  padding: 20px;
}
</style>
