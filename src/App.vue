<template>
  <main id="app">
    <header class="header">
      <Navbar />
    </header>
    <section class="products">
      <AddForm @addProduct="createCard" class="add-form" />
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
          src: "https://res.cloudinary.com/idaproject/image/upload/v1644162561/%D0%91%D0%B5%D0%B7_%D0%BD%D0%B0%D0%B7%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F_hnrtko.jpg",
          title: "Card title",
          description:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s",
          cost: "12.000",
        },
        {
          id: 2,
          src: "https://res.cloudinary.com/idaproject/image/upload/v1644162561/%D0%91%D0%B5%D0%B7_%D0%BD%D0%B0%D0%B7%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F_hnrtko.jpg",
          link: "",
          title: "Card title",
          description:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s",
          cost: "7.000",
        },
        {
          id: 3,
          src: "https://res.cloudinary.com/idaproject/image/upload/v1644162561/%D0%91%D0%B5%D0%B7_%D0%BD%D0%B0%D0%B7%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F_hnrtko.jpg",
          link: "",
          title: "Card title",
          description:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s",
          cost: "200.000",
        },
        {
          id: 4,
          src: "https://res.cloudinary.com/idaproject/image/upload/v1644162561/%D0%91%D0%B5%D0%B7_%D0%BD%D0%B0%D0%B7%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F_hnrtko.jpg",
          title: "Card title",
          description:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s",
          cost: "15.000",
        },
        {
          id: 5,
          src: "https://res.cloudinary.com/idaproject/image/upload/v1644162561/%D0%91%D0%B5%D0%B7_%D0%BD%D0%B0%D0%B7%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F_hnrtko.jpg",
          title: "Card title",
          description:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s",
          cost: "11.000",
        },

        {
          id: 6,
          src: "https://res.cloudinary.com/idaproject/image/upload/v1644162561/%D0%91%D0%B5%D0%B7_%D0%BD%D0%B0%D0%B7%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F_hnrtko.jpg",
          link: "",
          title: "Card title",
          description:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s",
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
<style scoped >
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
.product__list {
  display: flex;
  justify-content: start;
  flex-wrap: wrap;
}
@media (max-width: 560px) {
  #app {
    padding: 12px;
    margin: 0 auto;
    max-width: 1440px;
  }
  .product__list {
    display: flex;
    flex-direction: row;
    width: 100%;
    justify-content: center;
  }
}
</style>
