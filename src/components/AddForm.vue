<template>
  <div>
    <form v-show="!mobile" @submit.prevent>
      <label for="product__name">Наименование товара <span /></label>
      <input
        type="text"
        id="product__name"
        placeholder="Введите наименование товара"
        v-model="product.title"
      />
      <p v-show="inputChange" class="error">Поле является обязательным</p>
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
        v-model="product.src"
      />
      <label for="product__cost">Цена товара<span /></label>
      <input
        type="text"
        id="product__cost"
        placeholder="Введите цену"
        v-model="product.cost"
      />
      <div>
        <button type="button" @click="createCard" class="add__btn">
          Добавить товар
        </button>
      </div>
    </form>
    <button
      type="button"
      class="toggleFormBtn"
      @click="toggleMobileNav"
      v-show="mobile"
    >
      Добавить товар
    </button>
    <button
      type="button"
      class="toggleFormBtn close"
      @click="toggleMobileNav"
      v-show="mobileNav"
    >
      Закрыть модальное окно
    </button>
    <transition name="mobile-nav">
      <form v-show="mobileNav" @submit.prevent>
        <h2 v-show="mobile" class="add__item">Добавление товара</h2>
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
        <label for="product__link">
          Ссылка на изображение товара<span />
        </label>

        <input
          type="text"
          id="product__link"
          placeholder="Введите ссылку"
          v-model="product.src"
        />
        <label for="product__cost">Цена товара<span /></label>
        <input
          type="text"
          id="product__cost"
          placeholder="Введите цену"
          v-model="product.cost"
        />
        <div>
          <button type="button" @click="createCard" class="add__btn">
            Добавить товар
          </button>
        </div>
      </form>
    </transition>
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
      mobileNav: null,
      mobile: null,
      scrollPosition: null,
      windowWidth: null,
    };
  },
  created() {
    window.addEventListener("resize", this.checkScreen);
    this.checkScreen();
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
    toggleMobileNav() {
      this.mobileNav = !this.mobileNav;
    },
    checkScreen() {
      this.windowWidth = window.innerWidth;
      if (this.windowWidth <= 560) {
        this.mobile = true;
        return;
      }
      this.mobileNav = false;
      this.mobile = false;
      return;
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
  height: auto;
  border-radius: 4px;
  padding: 24px;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04),
    0px 6px 10px rgba(0, 0, 0, 0.02);
  margin: 0px 8px 8px;
  transition: 0.3s ease;
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
textarea {
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
.error {
  font-size: 12px;
  line-height: 4px;
  letter-spacing: -0.02em;
  color: #ff8484;
  margin-bottom: 16px;
}
form input::placeholder {
  color: #b4b4b4;
  font-size: 12px;
}
form textarea::placeholder {
  color: #b4b4b4;
  font-size: 12px;
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
  cursor: pointer;
}
.add__btn:hover {
  background: #7bae73;
  color: #ffffff;
}
.toggleFormBtn {
  position: fixed;
  top: 85%;
  right: 5%;
  z-index: 2;
  padding: 10px 16px;
  background: #fffefb;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  font-size: 16px;
  border: none;
  cursor: pointer;
  color: #b4b4b4;
  outline: none;
  text-align: center;
  transition: 0.3s ease;
}
.toggleFormBtn:hover {
  box-shadow: 0px 2px 5px rgba(1, 1, 1, 0.5);
  color: #222;
}
.mobile-nav-enter-active,
.mobile-nav-close-active {
  transition: 0.2s ease-in-out all;
}
.mobile-nav-enter-from,
.mobile-nav-leave-to {
  transform: translateX(-250px);
}
.mobile-nav-enter-to {
  transform: translateX(0);
}
@media (max-width: 560px) {
  form {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    max-width: 560px;
    padding: 20px;
    z-index: 20;
    background: #fff;
    justify-content: center;
    margin: auto;
  }
}
</style>
