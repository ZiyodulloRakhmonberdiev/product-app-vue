<template>
  <div class="navbar">
    <h2 class="add__item">Добавление товара</h2>
    <nav>
      <button class="modal__btn">Добавление товара</button>
      <my-select v-model="selectedSort" :option="selectedOptions" />
    </nav>
  </div>
</template>
<script>
import MySelect from "./MySelect.vue";
export default {
  name: "Navbar",
  components: { MySelect },
  data() {
    return {
      selectedSort: "",
      selectOptions: [
        { value: "name", name: "Filter by up" },
        { value: "title", name: "Filter by down" },
      ],
    };
  },
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
  /* margin-top: 6px; */
  height: 36px;
  font-size: 12px;
  /* line-height: 15px; */
  color: #b4b4b4;
  background: #eeeeee;
  border-radius: 10px;
  border: none;
  transition: 0.2s ease;
}
.modal__btn:hover {
  background: #7bae73;
  color: #ffffff;
}
.add__item {
  font-size: 28px;
  font-weight: 600;
  line-height: 35px;
  /* width: 100%; */
  margin-bottom: 16px;
}
</style>