<template>
  <div class="modal">
    <div class="popup" id="main">
      <div class="popup__overlay" @click.self="hidePopup('main')"></div>
      <div class="popup__content">
        <div class="popup__close">
          <img
            src="../assets/img/close.png"
            alt=""
            @click.self="hidePopup('main')"
          />
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

          <div class="preloader">
            <div class="sk-bounce-1 sk-child"></div>
            <div class="sk-bounce-2 sk-child"></div>
            <div class="sk-bounce-3 sk-child"></div>
          </div>
        </form>
      </div>
    </div>

    <div class="popup" id="success">
      <div class="popup__overlay" @click.self="hidePopup('success')"></div>
      <div class="popup__content">
        <div class="popup__close">
          <img
            src="../assets/img/close.png"
            alt=""
            @click.self="hidePopup('success')"
          />
        </div>
        <p class="popup__heading green">
          Спасибо! Мы скоро с вами свяжемся.
        </p>
      </div>
    </div>

    <div class="popup" id="error">
      <div class="popup__overlay" @click.self="hidePopup('error')"></div>
      <div class="popup__content">
        <div class="popup__close">
          <img
            src="../assets/img/close.png"
            alt=""
            @click.self="hidePopup('error')"
          />
        </div>
        <p class="popup__heading">
          Ой, что-то пошло не так... Попробуйте позже.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  methods: {
    validateForm(event) {
      const target = event.target;
      target.value = target.value
        .replace(/[^a-z0-9@s\-_.!~*']/gi, "")
        .replace(/-+/g, "-")
        .replace(/\.+/g, ".");
    },
    hidePopup(selector) {
      const popup = document.getElementById(selector);
      if (selector == "main") {
        popup.querySelector("form").reset();
      }
      popup.style.display = "";
    },
    sendForm(event) {
      const mainPopup = document.getElementById("main");
      const successPopup = document.getElementById("success");
      const errorPopup = document.getElementById("error");
      const preloader = document.querySelector(".preloader");

      preloader.style.visibility = "visible";
      const formData = new FormData(event.target);
      const body = {};
      for (const value of formData.entries()) {
        body[value[0]] = value[1];
      }

      fetch("https://jsonplaceholder.typicode.com/posts", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify(body),
      })
        .then((response) => {
          if (!response.ok) {
            throw new Error("network failed");
          }
          return response.json();
        })
        .then((data) => {
          console.log("Отправленные данные: ", data);

          preloader.style.visibility = "hidden";
          mainPopup.style.display = "";
          successPopup.style.display = "block";

          setTimeout(() => {
            successPopup.style.display = "";
          }, 3000);
        })
        .catch((error) => {
          console.error(error);

          preloader.style.visibility = "hidden";
          mainPopup.style.display = "";
          errorPopup.style.display = "block";

          setTimeout(() => {
            errorPopup.style.display = "";
          }, 3000);
        });
      event.target.reset();
    },
  },
};
</script>

<style lang="scss" scoped>
.popup {
  display: none;
  position: relative;
}
.popup__overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 10;
}
.popup__content {
  position: fixed;
  top: 35%;
  left: 0;
  right: 0;
  margin: 0 auto;
  background-color: white;
  border-radius: 10px;
  width: 35%;
  min-width: 310px;
  padding: 20px;
  z-index: 11;
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
.popup__heading {
  color: #26303b;
  font-weight: 700;
  font-size: 36px;
  line-height: 46px;
}
.green {
  color: #7db945;
  margin-bottom: 14px;
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
  font-size: 14px;
  line-height: 1.42857143;
  margin-bottom: 20px;
}
.form__button {
  color: white;
  cursor: pointer;
  background-color: #7db945;
  font-size: 22px;
  padding: 5% 11%;
  border-radius: 10px;
  font-family: "Rotonda C", sans-serif;
  border: none;
}

//стили прелоадера
.preloader {
  visibility: hidden;
  $spinkit-size: 4em;
  $spinkit-spinner-color: #7db945;
  $animationDuration: 1.4s;
  $delayRange: 0.32s;
  width: ($spinkit-size * 2);
  margin: auto;
  margin-top: 15px;
  text-align: center;

  .sk-child {
    width: ($spinkit-size / 2);
    height: ($spinkit-size / 2);
    background-color: $spinkit-spinner-color;

    border-radius: 100%;
    display: inline-block;
    animation: sk-three-bounce $animationDuration ease-in-out 0s infinite both;
  }

  .sk-bounce-1 {
    animation-delay: -$delayRange;
  }
  .sk-bounce-2 {
    animation-delay: (-$delayRange / 2);
  }
}

@keyframes sk-three-bounce {
  0%,
  80%,
  100% {
    transform: scale(0);
  }
  40% {
    transform: scale(1);
  }
}

@media only screen and (max-width: 320px) {
  .popup__heading {
    font-size: 22px;
    line-height: 34px;
}

}
</style>
