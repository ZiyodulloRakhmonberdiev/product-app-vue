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
          src: "https://res.cloudinary.com/idaproject/image/upload/v1644162561/%D0%91%D0%B5%D0%B7_%D0%BD%D0%B0%D0%B7%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F_ifawf6.png",
          title: "Он бы попросил вас прочитать. Это займет у вас 2 минуты",
          description:
            "Он считает, что будет более креативно донести свою точку зрения через задание, которое вы ему дадите.",
          cost: "12.000",
        },
        {
          id: 2,
          src: "https://res.cloudinary.com/idaproject/image/upload/v1644162563/%D0%91%D0%B5%D0%B7_%D0%BD%D0%B0%D0%B7%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F_3_kqcqwt.jpg",
          link: "",
          title: "Как вы думаете, он гений?",
          description:
            "Он не мог выполнить эту работу. Но он сделал все, что мог. Если бы в нем была атмосфера программиста, он бы преуспел. Он говорит, что достаточно много читать, чтобы быть хорошим программистом. Но чтобы быть хорошим человеком, нужно родиться хорошим человеком. Для него человечность всегда превыше всего",
          cost: "7.000",
        },
        {
          id: 3,
          src: "https://res.cloudinary.com/idaproject/image/upload/v1644163668/photo_2022-02-06_18-07-30_gfdx1t.jpg",
          link: "",
          title: "Он готов на все",
          description:
            "Он отказался от своей любимой библиотеки react, чтобы присоединиться к своей любимой команде, и попытался освоить упомянутый вами фреймворк за 3 дня без сна и еды. Потому что его любовь к idaproject сильнее всего ",
          cost: "200.000",
        },
        {
          id: 4,
          src: "https://res.cloudinary.com/idaproject/image/upload/v1644161688/photo_2022-02-06_17-33-23_v3ggkg.jpg",
          title: "Что вы думаете о своей компании?",
          description:
            "Он сходит с ума, когда отслеживает вашу компанию в социальных сетях. Потому что это идеальная семья и компания, о которых он мечтал. Он любит профессионализм. Вот почему он выбрал тебя. Не важно сколько зарплата, главное окружение. ",
          cost: "15.000",
        },
        {
          id: 5,
          src: "https://res.cloudinary.com/idaproject/image/upload/v1644163666/photo_2022-02-06_18-07-20_ll9etg.jpg",
          title: "Советую попытать счастья",
          description:
            "Если вы позволите ему стать членом вашей семьи, у вас будет мечтательный программист. Напомню, что в будущем он хочет стать Илоном Маском.",
          cost: "11.000",
        },

        {
          id: 6,
          src: "https://res.cloudinary.com/idaproject/image/upload/v1644162561/%D0%91%D0%B5%D0%B7_%D0%BD%D0%B0%D0%B7%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F_2_glgdzx.jpg",
          link: "",
          title: "Он узнает все это от вас",
          description:
            "Он не боится поражения. Он может встать на ноги для своей цели. Вы просто открываете ему двери, он делает все остальное. Если вам интересно, вы можете встретиться с ним за чашечкой кофе. Он ожидает, что вы наймете его. С уважением он, то есть я!",
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
.header .select option {
  font-size: 12px;
  line-height: 15px;
  color: #b4b4b4;
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
}
.modal__btn:hover {
  background: #7bae73;
  color: #ffffff;
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