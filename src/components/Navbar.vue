<template>
  <div class="navbar">
    <h2 class="add__item">Добавление товара</h2>
    <nav>
      <button class="modal__btn">Добавление товара</button>
      <SortByPrice />
    </nav>
  </div>
</template>
<script>
import SortByPrice from "./SortByPrice.vue";
export default {
  name: "Navbar",
  components: { SortByPrice },
};
</script>
<style>
.navbar {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.modal__btn {
  width: auto;
  height: 36px;
  font-size: 12px;
  color: #b4b4b4;
  background: #eeeeee;
  border-radius: 10px;
  border: none;
  transition: 0.2s ease;
  display: none;
}
.modal__btn:hover {
  background: #7bae73;
  color: #ffffff;
}
.add__item {
  font-size: 28px;
  font-weight: 600;
  line-height: 35px;
  margin-bottom: 16px;
}
</style>