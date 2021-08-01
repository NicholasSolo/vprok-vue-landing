<template>
  <section class="bonus">
    <div class="bonus__сards">
      <div class="card">
        <img
          src="../assets/img/discount.png"
          alt="discount"
          class="card__icon"
        />
        <div class="card__description">
          <div class="card__headings">
            <p class="card__heading top">Скидка&nbsp;</p>
            <p class="card__heading green">1500 ₽</p>
          </div>
          <p class="card-text">
            <span>–500 ₽</span> на первые три заказа<br />
            по промокоду NEW
          </p>
        </div>
      </div>
      <div class="plus">+</div>
      <div class="card">
        <img
          src="../assets/img/delivery.png"
          alt="discount"
          class="card__icon"
        />
        <div class="card__description">
          <p class="card__heading top">Бесплатная</p>
          <p class="card__heading green">доставка</p>
          <p class="card-text">
            первого заказа
          </p>
        </div>
      </div>
    </div>
    <button class="bonus__purchase" @click="showPopup">К покупкам</button>
    <Modal />
  </section>
</template>

<script>
import Modal from "./Modal.vue";
export default {
  name: "Bonus",
  data() {
    return {};
  },
  methods: {
    showPopup() {
      const popup = document.getElementById("main");
      popup.style.display = "block";
    },
  },
  components: {
    Modal,
  },
};
</script>

<style lang="scss" scoped>
.bonus {
  padding-top: 60px;
  background-color: white;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.bonus__сards {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  margin-bottom: 50px;
}
.card {
  padding: 30px;
  display: flex;
  border: 1px solid #d0d4cd;
  height: 217px;
  width: 390px;
  img {
    width: 70px;
    height: 70px;
    margin-right: 30px;
  }
}
.card__description {
  text-align: left;
}
.card__heading {
  color: #26303b;
  font-weight: 700;
  font-size: 36px;
  line-height: 46px;
}
.green {
  color: #7db945;
  margin-bottom: 14px;
}
.top {
  margin-top: 10px;
}
.card-text {
  font-size: 16px;
  line-height: 24px;
  font-weight: 400;
  span {
    font-weight: 700;
  }
}
.plus {
  color: #26303b;
  font-size: 36px;
  line-height: 46px;
  font-weight: 700;
  width: 104px;
}
.bonus__purchase {
  cursor: pointer;
  color: white;
  background-color: #7db945;
  font-size: 22px;
  font-weight: 700;
  line-height: 36px;
  padding: 17px 111px;
  margin-bottom: 100px;
  border-radius: 10px;
  font-family: "Rotonda C";
  border: none;
}

@media only screen and (max-width: 920px) {
  .bonus__сards {
    flex-direction: column;
  }
}
@media only screen and (max-width: 400px) {
  .card {
    padding: 30px;
    display: flex;
    align-items: center;
    height: 220px;
    width: 280px;
    img {
      width: 60px;
      height: 60px;
      margin-right: 0px;
      margin-bottom: 20px;
    }
  }
  .bonus__purchase {
    padding: 17px 90px;
  }
}

@media only screen and (max-width: 320px) {
  .bonus {
    padding-top: 30px;
  }
  .bonus__сards {
    margin-bottom: 30px;
  }
  .card {
    padding: 30px;
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 220px;
    width: 280px;
    img {
      width: 60px;
      height: 60px;
      margin-right: 0px;
      margin-bottom: 20px;
    }
  }
  .card__description {
    text-align: center;
    display: flex;
    flex-direction: column;
  }
  .card__headings {
    display: flex;
  }
  .card__heading {
    font-size: 30px;
    line-height: 32px;
  }
  .card-text {
    font-size: 14px;
    line-height: 22px;
  }
  .top {
    margin: 0px;
  }
  .green {
    margin-bottom: 0px;
  }
  .plus {
    height: 83px;
    padding-top: 20px;
  }

  .bonus__purchase {
    font-size: 22px;
    font-weight: 700;
    line-height: 36px;
    padding: 17px 80px;
    margin-bottom: 80px;
  }
}
</style>
