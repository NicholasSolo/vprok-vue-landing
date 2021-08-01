<template>
  <section class="carousel">
    <h1 class="carousel__heading">
      Взгляните на процесс сборки своими глазами
    </h1>
    <div class="slider">
      <div class="swiper-container">
        <div class="swiper-wrapper">
          <div class="swiper-slide" v-for="slide of slides" :key="slide.id">
            <div class="slide__img">
              <div class="slide__number">
                <p>{{ slide.slideNumber }}</p>
              </div>
              <img :src="slide.slideImg" :alt="slide.slideHeading" />
            </div>
            <div class="slide__description">
              <p class="slide__heading">{{ slide.slideHeading }}</p>
              <p class="slide__text">{{ slide.slideText }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="slider__arrows">
      <img
        class="arrow-left"
        src="../assets/img/arrow-left.svg"
        alt="arrow-left"
      />
      <img
        class="arrow-right"
        src="../assets/img/arrow-right.svg"
        alt="arrow-right"
      />
    </div>
  </section>
</template>

<script>
import Swiper from "swiper/bundle";

import step1 from "../assets/img/step1.png";
import step2 from "../assets/img/step2.png";
import step3 from "../assets/img/step3.png";
import step4 from "../assets/img/step4.png";
import step5 from "../assets/img/step5.png";

export default {
  name: "Carousel",
  data() {
    return {
      slides: [
        {
          slideNumber: "1",
          slideImg: step1,
          slideHeading: "Привезём точно по списку",
          slideText:
            "Сборщик берет с собой наручный терминал, на котором он видит весь список покупок для каждого заказа.",
        },
        {
          slideNumber: "2",
          slideImg: step2,
          slideHeading: "Собираем быстро и эффективно",
          slideText:
            "Для улучшения эргономики пространства товары размещены от тяжёлых к лёгким, находящимся уже в конечной зоне упаковки.",
        },
        {
          slideNumber: "3",
          slideImg: step3,
          slideHeading: "За свежесть и качество отвечаем",
          slideText:
            "Выделены специальные зоны, в том числе холодная и морозильная.",
        },
        {
          slideNumber: "4",
          slideImg: step4,
          slideHeading: "Шампунь не положат рядом с рыбой",
          slideText:
            "Собираем и упаковываем ваш заказ с заботой: соблюдаем принципы товарного соседства и учитываем вес товара.",
        },
        {
          slideNumber: "5",
          slideImg: step5,
          slideHeading: "Довезём в сохранности даже яйца",
          slideText:
            "Бережно транспортируем контейнеры, фиксируя их стяжными ремнями. Системы охлаждения поддерживают температурный режим.",
        },
      ],
    };
  },
  mounted() {
    const swiperContainer = document.querySelector(".swiper-container");
    new Swiper(swiperContainer, {
      loop: true,
      autoplay: {
        delay: 3000,
      },
      navigation: {
        nextEl: ".arrow-right",
        prevEl: ".arrow-left",
      },
    });
  },
};
</script>

<style lang="scss" scoped>
@import "../../node_modules/swiper/swiper-bundle.css";
.carousel {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.carousel__heading {
  font-weight: 700;
  font-size: 36px;
  line-height: 46px;
  color: #26303b;
  max-width: 500px;
  margin-bottom: 30px;
}
.slider {
  max-width: 640px;
  width: 100%;
  padding: 40px;
  margin: 0px 15px 80px;
  background-color: white;
  border-radius: 5px;
}
.slide__img {
  margin-bottom: 28px;
  position: relative;
  img {
    max-width: 560px;
    width: 100%;
    max-height: 284px;
    height: 100%;
  }
}
.slide__number {
  display: flex;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: white;
  color: #7db945;
  font-weight: 700;
  font-size: 22px;
  position: absolute;
  top: -14px;
  left: -8px;
  padding-top: 10px;

  p {
    margin: auto;
  }
}
.slide__description {
  font-size: 16px;
  line-height: 24px;
}
.slide__heading {
  font-weight: 700;
}
.slider__arrows {
  position: absolute;
  width: 750px;
  display: flex;
  justify-content: space-between;
  top: 55%;
  img {
    cursor: pointer;
  }
}

@media only screen and (max-width: 800px) {
  .slider__arrows {
    width: 150px;
    top: 91%;
  }
}
@media only screen and (max-width: 400px) {
  .carousel__heading {
    font-size: 30px;
  }
  .slider {
    padding: 30px 30px 10px 30px;
  }
  .slider__arrows {
    width: 140px;
    top: 89%;
  }
}
@media only screen and (max-width: 320px) {
  .carousel__heading {
    font-weight: 700;
    font-size: 26px;
    line-height: 32px;
    max-width: 500px;
    margin-bottom: 33px;
  }
  .slide__description {
    font-size: 14px;
    line-height: 22px;
  }
  .slider {
    max-width: 280px;
    width: 100%;
    padding: 20px 20px 16px 20px;
    margin: 0px 20px 112px;
    background-color: white;
    border-radius: 5px;
  }
  .slide__img {
    margin-bottom: 20px;
    position: relative;
    img {
      max-width: 240px;
      width: 240px;
      max-height: 160px;
      height: 160px;
    }
  }
  .slider__arrows {
    width: 140px;
    top: 86%;
  }
}
</style>
