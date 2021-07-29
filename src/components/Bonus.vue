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
          <p class="card__heading top">Скидка</p>
          <p class="card__heading green">1500 ₽</p>
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

    <div class="popup" @click.self="hidePopup">
      <div class="popup__content">
        <div class="popup__close">
          <img src="../assets/img/close.png" alt="" @click.self="hidePopup" />
        </div>
        <form id="form" name="email-form" @submit.prevent="sendForm">
          <input
            @input="validateForm"
            class="form__email"
            type="email"
            placeholder="Введите email"
            name="email-address"
            id="email"
            required
          />
          <button class="form__button" type="submit">Отправить</button>
        </form>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Bonus",
  data() {
    return {};
  },
  methods: {
    validateForm(event) {
      const target = event.target;
      target.value = target.value
        .replace(/[^a-z0-9@s\-_.!~*']/gi, "")
        .replace(/-+/g, "-")
        .replace(/\.+/g, ".");
    },
    showPopup() {
      const popup = document.querySelector(".popup");
      popup.style.display = "block";
    },
    hidePopup() {
      const popup = document.querySelector(".popup");
      popup.style.display = "";
    },
    sendForm(event) {
      const formData = new FormData(event.target);
      const body = {};
      for (const value of formData.entries()) {
        body[value[0]] = value[1];
      }

      fetch("адрес__сервера", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify(body),
      })
        .then((response) => {
          if (response.status !== 200) {
            throw new Error("network failed");
          }
          return response.json();
        })
        .then((data) => {
          console.log("отправленные данные: ", data);
        })
        .catch((error) => {
          console.error(error);
        });
      event.target.reset();
    },
  },
};
</script>

<style lang="scss" scoped>
.bonus {
  border: 2px solid red;
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

//стили попапа
.popup {
  display: none;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 10;
}
.popup__content {
  position: fixed;
  top: 32%;
  left: 37%;
  background-color: white;
  border-radius: 10px;
  width: 500px;
  padding: 20px;
}
.popup__close {
  width: 100%;
  display: flex;
  justify-content: flex-end;
  margin-bottom: 15px;
  img {
    cursor: pointer;
    width: 30px;
    height: 30px;
  }
}
.form__email {
  display: block;
  width: 100%;
  height: 52px;
  padding: 0 40px 0 20px;
  border: 2px solid #e3e3e4;
  border-radius: 0;
  background: #fff;
  color: #727376;
  text-shadow: none;
  font-size: 14px;
  line-height: 1.42857143;
  margin-bottom: 20px;
}
.form__button {
  color: white;
  cursor: pointer;
  background-color: #7db945;
  font-size: 22px;
  padding: 17px 60px;
  border-radius: 10px;
  font-family: "Rotonda C";
  border: none;
}
</style>
