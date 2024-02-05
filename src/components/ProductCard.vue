<template>
  <div class="product-card">
    <img :src="productIcon" alt="Product Icon" class="product-icon">
    <h3 class="product-title">{{ productTitle }}</h3>
    <div class="cart-section">
      <button v-if="cartCount > 0" @click="decrementCount" class="cart-button">-</button>
      <p v-if="cartCount > 0" class="cart-count">{{ cartCount }}</p>
      <button v-if="cartCount > 0" @click="incrementCount" class="cart-button">+</button>
      <button v-else @click="addToCart" class="buy-button">Купить</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductCard',
  props: {
    productIcon: {
      type: String,
      required: true,
    },
    productTitle: {
      type: String,
      required: true,
    },
    cartCount: {
      type: Number,
      default: 0,
    },
  },
  methods: {
    addToCart() {
      // Логика добавления продукта в корзину
      this.$emit('add-to-cart');
    },
    decrementCount() {
      // Логика уменьшения количества продуктов в корзине
      this.$emit('decrement-count');
    },
    incrementCount() {
      // Логика увеличения количества продуктов в корзине
      this.$emit('increment-count');
    },
  },
};
</script>

<style scoped>
.product-card {
  width: 100px;
  /*height: 120px;*/
  text-align: center;
  border: 1px solid #ccc;
  padding: 10px;
  margin: 10px;
}

.product-icon {
  width: 100px;
  height: 100px;
}

.product-title {
  margin: 10px 0;
}

.cart-section {
  display: flex;
  align-items: center;
  justify-content: center;
}

.cart-count {
  margin-right: 5px;
  margin-left: 5px;
  font-weight: bold;
}

.cart-button {
  background-color: #3498db;
  color: #fff;
  border: none;
  border-radius: 5px;
  padding: 5px 10px;
  cursor: pointer;
}

.buy-button {
  background-color: #27ae60;
  color: #fff;
  border: none;
  border-radius: 5px;
  padding: 5px 10px;
  cursor: pointer;
}
</style>
