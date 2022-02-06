<template>
  <div class="product">
    <div class="product-inner">
      <div class="product-image-wrap">
        <img :src="product.src" class="image" />
      </div>
      <div class="product-text-wrap">
        <h2 class="card-title">{{ product.title }}</h2>
        <h2 class="card-description">{{ product.description }}</h2>
        <h2 class="card-cost">{{ product.cost }}</h2>
      </div>
      <button class="delete-button" @click="$emit('remove', product)">
        <i class="fas fa-trash-alt"></i>
      </button>
    </div>
  </div>
</template>
<script>
export default {
  name: "product",
  props: ["product"],
};
</script>
<style scoped>
.product {
  max-width: 310px;
  margin: 16px 0 16px 16px;
  position: relative;
  transition: 2s ease;
  background: #fffefb;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04),
    0px 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: 4px;
}
.product-image-wrap {
  width: 312px;
  height: 200px;
}
.product-image-wrap img {
  object-fit: cover;
  width: 100%;
  height: 100%;
}
.product-text-wrap {
  padding: 16px;
}
.product-text-wrap .card-title {
  font-weight: 600;
  font-size: 20px;
  line-height: 25px;
  color: #3f3f3f;
}
.card-cost {
  font-weight: 600;
  font-size: 24px;
  margin-bottom: 0;
  color: #3f3f3f;
}

.product-text-wrap .card-description {
  font-weight: normal;
  font-size: 16px;
  line-height: 20px;
  color: #3f3f3f;
}
.delete-button {
  position: absolute;
  right: -8px;
  top: 0;
  transform: translateY(-8px);
  width: 32px;
  height: 32px;
  background: #ff8484;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  display: none;
  border: none;
  cursor: pointer;
}
.delete-button:hover {
  background: #ff5099;
}
.fa-trash-alt {
  color: #ffffff;
  font-weight: normal;
}
.product:hover .delete-button {
  display: flex;
  transition: 0.2s ease;
}
</style>