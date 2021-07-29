<template>
  <footer class="footer">
    <a class="footer__logo" href="https://www.vprok.ru/" target="blank">
      <img src="../assets/img/brand-logo.png" alt="vprok-logo" />
    </a>
    <div class="footer-contact">
      <div class="phones">
        <div class="city">
          <div class="city-name">Москва</div>
          <div class="phone-number">+7 495 797-57-77</div>
        </div>
        <div class="city">
          <div class="city-name">Санкт-Петербург</div>
          <div class="phone-number">+7 812 385-99-55</div>
        </div>
      </div>
      <div class="social">
        <a href="#">
          <img
            src="../assets/img/facebook.svg"
            alt="facebook"
            class="social-logo"
          />
        </a>
        <a href="#">
          <img src="../assets/img/vk.svg" alt="vk" class="social-logo" />
        </a>
        <a href="#">
          <img src="../assets/img/insta.svg" alt="insta" class="social-logo" />
        </a>
        <a href="#">
          <img src="../assets/img/ok.svg" alt="ok" class="social-logo" />
        </a>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style lang="scss" scoped>
.footer {
  border: 2px solid chartreuse;
  padding: 47px 262px 0px;
  background-color: #043e44;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  color: white;
}
.footer__logo {
  margin-bottom: 15px;
}
.footer-contact {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 107px;
}
.phones {
  display: flex;
  text-align: left;
  margin-right: 245px;
}
.city {
  margin-right: 40px;
}
.city-name {
  font-size: 14px;
  line-height: 36px;
  font-weight: 400;
}
.phone-number {
  font-weight: 700;
  font-size: 22px;
  line-height: 36px;
}
.social {
  display: flex;
  align-items: center;
}
.social-logo {
  margin-right: 40px;
}
</style>
