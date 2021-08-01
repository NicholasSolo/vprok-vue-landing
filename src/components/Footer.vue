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
        <div class="city no-mr">
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
          <img src="../assets/img/ok.svg" alt="ok" class="social-logo no-mr" />
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
  padding: 47px 262px 107px;
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
  width: 100%;
}
.phones {
  display: flex;
  text-align: left;
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
.no-mr {
  margin-right: 0px;
}

@media only screen and (max-width: 1366px) {
  .footer {
    padding: 47px 150px 107px;
  }
}
@media only screen and (max-width: 1280px) {
  .footer {
    padding: 47px 100px 107px;
  }
}
@media only screen and (max-width: 1024px) {
  .footer {
    padding: 47px 54px 107px;
  }
}
@media only screen and (max-width: 768px) {
  .footer-contact {
    flex-direction: column;
    align-items: start;
  }
  .phones {
    flex-direction: column;
  }
}
@media only screen and (max-width: 520px) {
  .footer {
    padding: 47px 44px 35px;
  }
  .phones {
    flex-direction: column;
  }
}
@media only screen and (max-width: 320px) {
  .footer {
    padding: 46px 46px 77px 46px;
  }
  .footer__logo {
    margin-bottom: 15px;
    img {
      width: 131px;
      height: 37px;
    }
  }
  .footer-contact {
    flex-direction: column;
  }
  .phones {
    margin-bottom: 15px;
  }
}
</style>
