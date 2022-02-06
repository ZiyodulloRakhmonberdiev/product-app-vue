<template>
  <main id="app">
    <header class="header">
      <Navbar />
    </header>
    <section class="products">
      <AddForm @addProduct="createCard" />
      <ProductList :products="products" @remove="removeProduct" />
    </section>
  </main>
</template>
<script>
import ProductList from "./components/ProductList.vue";
import AddForm from "./components/AddForm.vue";
import Navbar from "./components/Navbar.vue";
export default {
  name: "app",
  components: {
    AddForm,
    ProductList,
    Navbar,
  },
  data() {
    return {
      products: [
        {
          id: 1,
          src: require("./assets/Rectangle31.png"),
          link: "",
          title: "Наименование товара",
          description:
            "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          cost: "12.000",
        },
        {
          id: 2,
          src: require("./assets/Rectangle31.png"),
          link: "",
          title: "Наименование товара",
          description:
            "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          cost: "15.000",
        },
        {
          id: 3,
          src: require("./assets/Rectangle31.png"),
          link: "",
          title: "Наименование товара",
          description: "Довольно-таки интересное описание товара в ",
          cost: "11.000",
        },
        {
          id: 4,
          src: require("./assets/Rectangle31.png"),
          link: "",
          title: "Наименование товара",
          description:
            "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          cost: "2.000",
        },
        {
          id: 5,
          src: require("./assets/Rectangle31.png"),
          link: "",
          title: "Наименование товара",
          description:
            "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          cost: "7.000",
        },
        {
          id: 6,
          src: require("./assets/Rectangle31.png"),
          link: "",
          title: "Наименование товара",
          description:
            "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          cost: "1.000",
        },
      ],
    };
  },
  methods: {
    createCard(product) {
      this.products.push(product);
    },
    removeProduct(product) {
      this.products = this.products.filter((c) => c.id !== product.id);
    },
  },
};
</script>
<style scoped>
* {
  font-family: Source Sans Pro, sans-serif;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
#app {
  padding: 22px;
  margin: 0 auto;
  max-width: 1440px;
}
.products {
  display: flex;
  flex-direction: row;
}
.add__item {
  font-size: 28px;
  font-weight: 600;
  line-height: 35px;
  width: 100%;
  margin-bottom: 16px;
}
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.header .select option {
  font-size: 12px;
  line-height: 15px;
  color: #b4b4b4;
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
</style>