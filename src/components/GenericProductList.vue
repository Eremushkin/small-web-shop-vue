<template>
  <div class="generic-product-list">
    <div class="generic-product-list-item">
      <slot></slot>
    </div>
  </div>
</template>

<script>

export default {
  name: 'GenericProductList',
};
</script>

<style scoped>
.generic-product-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

</style>
