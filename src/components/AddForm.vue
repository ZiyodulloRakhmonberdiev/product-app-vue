<template>
  <div>
    <form @submit.prevent>
      <label for="product__name">Наименование товара <span /></label>
      <input
        type="text"
        id="product__name"
        placeholder="Введите наименование товара"
        v-model="product.title"
      />
      <label for="product__description">Описание товара</label>
      <textarea
        id="product__description"
        cols="30"
        rows="6"
        placeholder="Введите описание товара"
        v-model="product.description"
      />
      <label for="product__link"> Ссылка на изображение товара<span /> </label>

      <input
        type="text"
        id="product__link"
        placeholder="Введите ссылку"
        v-model="product.link"
      />
      <label for="cost">Цена товара<span /></label>
      <input
        type="text"
        id="cost__link"
        placeholder="Введите цену"
        v-model="product.cost"
      />
      <div>
        <button type="button" @click="createCard" class="add__btn">
          Добавить товар
        </button>
      </div>
    </form>
  </div>
</template>
<script>
export default {
  name: "AddForm",
  data() {
    return {
      product: {
        id: "",
        title: "",
        description: "",
        link: "",
        cost: "",
        src: "",
      },
    };
  },
  methods: {
    createCard() {
      this.product.id = Date.now();
      this.$emit("addProduct", this.product);
      this.product = {
        id: "",
        src: "",
        link: "",
        title: "",
        description: "",
        cost: "",
      };
    },
  },
};
</script>
<style scoped >
form {
  display: flex;
  flex-direction: column;
  max-width: 332px;
  max-height: 440px;
  border-radius: 4px;
  padding: 24px;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04),
    0px 6px 10px rgba(0, 0, 0, 0.02);
  margin: 0px 8px 8px;
}
form label {
  position: relative;
  font-size: 10px;
  font-weight: 400;
}
form label span {
  position: absolute;
  width: 4px;
  height: 4px;
  top: 1px;
  background: #ff8484;
  border-radius: 4px;
}
form input,
textarea,
.custom-file-upload {
  margin-top: 4px;
  margin-bottom: 16px;
  padding-left: 16px;
  padding-bottom: 10px;
  padding-top: 10px;
  font-size: 12px;
  font-weight: 400;
  outline: none;
  background: #fffefb;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  border: none;
  resize: none;
}
form input::placeholder,
.custom-file-upload {
  color: #b4b4b4;
  font-size: 12px;
}
form textarea::placeholder {
  color: #b4b4b4;
  font-size: 12px;
}
input[type="file"] {
  display: none;
}
.add__btn {
  width: 100%;
  margin-top: 6px;
  height: 36px;
  font-size: 12px;
  line-height: 15px;
  color: #b4b4b4;
  background: #eeeeee;
  border-radius: 10px;
  border: none;
  transition: 0.2s ease;
}
.add__btn:hover {
  background: #7bae73;
  color: #ffffff;
}
</style>
