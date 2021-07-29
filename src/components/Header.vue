<template>
  <header>
    <div class="header__wrapper">
      <a class="header__logo" href="https://www.vprok.ru/" target="blank">
        <img src="../assets/img/brand-logo.png" alt="vprok-logo" />
      </a>
      <h1 class="header__title">{{ transformText("что такое даркстор?") }}</h1>
      <p class="header__description">
        Это магазин-склад без покупателей. <br />
        Именно здесь, а не в розничном магазине<br />
        собирают ваши заказы.
      </p>
    </div>
    <div class="swipe-down">
      <img src="../assets/img/swipe-icon.png" alt="swipe-icon" />
      <p>Свайп вниз</p>
    </div>
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
  border: 2px solid green;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  text-align: left;
  background-image: url("../assets/img/header-background.png");
  background-repeat: no-repeat;
  // background-size: contain;
  height: 530px;
  margin-bottom: 95px;
  color: #ffffff;
}
.header__wrapper {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin: 60px 0px 0px 260px;
}
.header__logo {
  margin-bottom: 125px;
}
.header__title {
  margin-bottom: 15px;
  font-weight: bold;
  font-size: 54px;
  line-height: 60px;
  letter-spacing: 0.02em;
}
.header__description {
  margin-bottom: 34px;
  font-size: 26px;
  line-height: 44px;
  letter-spacing: 0.02em;
}
.swipe-down {
  align-self: center;
  display: flex;
  align-items: center;
  margin-bottom: 29px;
  img {
    margin-right: 9px;
  }
}
</style>
