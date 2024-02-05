<template>
  <div class="local-impl">
    <ProductCard
        :productIcon="require('@/assets/product-icon-demo.png')"
        productTitle="Fish"
        :cartCount="localCardCount"
        @add-to-cart="addToCart"
        @decrement-count="decrementCount"
        @increment-count="incrementCount"
    />
  </div>
</template>

<script>
import ProductCard from '@/components/ProductCard.vue';

export default {
  name: 'LocalIncrementProductCard',
  components: {
    ProductCard
  },
  data() {
    return {
      localCardCount: 0
    }
  },
  methods: {
    addToCart() {
      // Логика добавления продукта в корзину
      this.localCardCount++;
    },
    decrementCount() {
      // Логика уменьшения количества продуктов в корзине
      if (this.localCardCount > 0) {
        this.localCardCount--;
      }
    },
    incrementCount() {
      // Логика увеличения количества продуктов в корзине
      this.localCardCount++;
    },
  }
}
</script>