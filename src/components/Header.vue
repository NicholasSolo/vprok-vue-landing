<template>
  <header class="header">
    <div class="header__wrapper">
      <a class="header__logo" href="https://www.vprok.ru/" target="blank">
        <img src="../assets/img/brand-logo.svg" alt="vprok-logo" />
      </a>
      <h1 class="header__title">{{ transformText("что такое даркстор?") }}</h1>
      <p class="header__description">
        Это магазин-склад без покупателей. Именно здесь, а не в розничном
        магазине собирают ваши заказы.
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
.header {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  text-align: left;
  background-image: url("../assets/img/header-background.png");
  background-repeat: no-repeat;
  background-size: 100% 100%;
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
  margin-bottom: 115px;
}
.header__title {
  margin-bottom: 15px;
  font-weight: bold;
  font-size: 54px;
  line-height: 60px;
  letter-spacing: 0.02em;
}
.header__description {
  max-width: 539px;
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
@media only screen and (max-width: 1024px) {
  .header {
    margin-bottom: 63px;
    clip-path: ellipse(100% 75% at 50% 25%);
  }
  .header__wrapper {
    margin: 100px 0px 0px 128px;
  }
  .header__logo {
    margin-bottom: 86px;
  }
  .header__title {
    margin-bottom: 12px;
    font-weight: bold;
    font-size: 40px;
    line-height: 44px;
    letter-spacing: 0.02em;
  }
  .header__description {
    max-width: 375px;
    margin-bottom: 30px;
    font-size: 20px;
    line-height: 32px;
  }
}
@media only screen and (max-width: 1024px) {
  .header {
    clip-path: ellipse(100% 73% at 50% 25%);
  }
}
@media only screen and (max-width: 900px) {
  .header {
    background-size: auto;
    background-position: 32%;
  }
}
@media only screen and (max-width: 650px) {
  header {
    margin-bottom: 43px;
    clip-path: ellipse(100% 73% at 50% 25%);
  }
  .header__wrapper {
    margin: 70px 0px 0px 88px;
  }
  .header__logo {
    margin-bottom: 63px;
  }
  .header__title {
    margin-bottom: 12px;
    font-weight: bold;
    font-size: 32px;
    line-height: 40px;
    letter-spacing: 0.02em;
  }
  .header__description {
    margin-bottom: 30px;
    font-size: 20px;
    line-height: 32px;
  }
}
@media only screen and (max-width: 490px) {
  .header {
    clip-path: ellipse(110% 73% at 50% 25%);
  }
  .header__wrapper {
    margin: 50px 0px 0px 68px;
  }
  .swipe-down {
    display: none;
  }
}
@media only screen and (max-width: 320px) {
  .header {
    padding: 40px 25px 53px 25px;
    margin-bottom: 40px;
    text-align: center;
    -webkit-clip-path: ellipse(156% 75% at 50% 25%);
    clip-path: ellipse(156% 75% at 50% 25%);
    background-size: 309%;
    background-position: 42% 57%;
  }
  .header__wrapper {
    margin: 0px;
    align-items: center;
  }
  .header__logo {
    margin-bottom: 70px;
    img {
      width: 100px;
      height: 28px;
    }
  }
  .header__title {
    max-width: 270px;
    margin-bottom: 26px;
    font-size: 28px;
    line-height: 36px;
  }
  .header__description {
    margin: 0px;
    font-size: 16px;
    line-height: 22px;
  }
  .swipe-down {
    display: none;
  }
}
</style>
