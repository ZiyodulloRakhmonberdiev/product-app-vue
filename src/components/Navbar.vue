<template>
  <div class="navbar">
    <h2 class="add__item">Добавление товара</h2>
    <nav>
      <SortByPrice class="sort" />
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
.add__item {
  font-size: 28px;
  font-weight: 600;
  line-height: 35px;
  margin-bottom: 16px;
}
@media (max-width: 560px) {
  .add__item {
    font-size: 24px;
    font-weight: 500;
    margin-bottom: 16px;
  }
  .navbar {
    position: fixed;
    left: 0;
    padding-top: 80px !important;
    padding-bottom: 30px !important;
    z-index: 10;
    background: #ffffff;
    flex-direction: column;
    justify-content: flex-end;
    border-bottom: 1px solid #999;
  }
}
</style>