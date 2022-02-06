<template>
  <div class="product__list" v-if="products.length > 0">
    <transition-group name="list">
      <Product
        v-for="product in products"
        :product="product"
        :key="product.id"
        @remove="$emit('remove', product)"
      />
    </transition-group>
  </div>
  <div v-else class="not__found">
    <p class="not__found-text">
      There is no product. Because you turned them off. <br />
      You can add them via the form. It is on the left side of the screen.
    </p>
  </div>
</template>
<script>
import Product from "./Product";
export default {
  props: {
    products: {
      type: Array,
      required: true,
    },
  },
  components: {
    Product,
  },
};
</script>
<style scoped>
.product__list {
  display: flex;
  justify-content: start;
  flex-wrap: wrap;
}
.not__found {
  width: 60%;
  display: flex;
  justify-content: center;
}
.not__found-text {
  font-size: 24px;
  color: #3f3f3f;
  text-align: center;
}
.list-item {
  display: inline-block;
  margin-right: 10px;
}
.list-enter-active,
.list-leave-active {
  transition: all 0.2s ease;
}
.list-enter-from,
.list-leave-to {
  opacity: 0;
  transform: translateY(30px);
}
</style>
