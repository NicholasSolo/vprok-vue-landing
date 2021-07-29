<template>
  <header>
    <a class="header__logo" href="#"
      ><img src="../assets/img/brand-logo.png" alt=""
    /></a>
    <h1 class="header__title">{{ transformText("что такое даркстор?") }}</h1>
    <p class="header__description">
      Это магазин-склад без покупателей. <br />
      Именно здесь, а не в розничном магазине<br />
      собирают ваши заказы.
    </p>
  </header>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {};
  },
  methods: {
    transformText(value) {
      return value.toUpperCase();
    },
  },
};
</script>

<style lang="scss" scoped>
    header {
        border: 1px solid green;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        text-align: left;
        // justify-content: center;
        padding: 60px 0px 0px 260px;
        background-image: url("../assets/img/header-background.png");
        background-repeat: no-repeat;
        background-size: cover;
        height: 530px;
        color: #ffffff;
    }
    .header__title {
        font-weight: bold;
        font-size: 54px;
        line-height: 60px;
        letter-spacing: 0.02em;
    }
    .header__description {
        font-size: 26px;
        line-height: 44px;

        letter-spacing: 0.02em;
    }
</style>
