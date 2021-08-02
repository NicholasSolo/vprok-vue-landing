<template>
  <div class="advantages">
    <h1 class="advantages__heading">Преимущества даркстора</h1>
    <div class="advantages__wrapper">
      <AdvantageCard
        v-for="(tile, index) in advantagesTiles"
        :key="index"
        :tile="tile"
      />
    </div>
  </div>
</template>

<script>
import tile1 from "../assets/img/tile1.png";
import tile2 from "../assets/img/tile2.png";
import tile3 from "../assets/img/tile3.png";
import tile4 from "../assets/img/tile4.png";
import tile5 from "../assets/img/tile5.png";
import tile6 from "../assets/img/tile6.png";

import AdvantageCard from "./AdvantageCard.vue";
export default {
  name: "Advantages",
  components: {
    AdvantageCard,
  },
  data() {
    return {
      advantagesTiles: [
        {
          tileImg: tile1,
          tileHeading: "Нет контакта с посторонними людьми",
          tileText:
            "Заказ формируется из товаров, до которых никто не дотрагивался, как это возможно на полках обычного магазина. Фрукты и овощи отбираются сборщиком вручную.",
        },
        {
          tileImg: tile2,
          tileHeading: "Заморозка 1 раз",
          tileText:
            "Продукты замораживаются однократно и поддерживаются в этом состоянии, пока не будут доставлены к вам.",
        },
        {
          tileImg: tile3,
          tileHeading: "Профессиональные морозильные камеры",
          tileText:
            "Товар хранится в промышленных холодильных и морозильных зонах с оптимальными температурными режимами для разных товаров: овощей, фруктов, масла и т. д.",
        },
        {
          tileImg: tile4,
          tileHeading: "Разделка мяса и рыбы под заказ",
          tileText:
            "Мясо и рыба разделываются непосредственно для вас, а при транспортировке хранятся в специальных боксах с низкой температурой.",
        },
        {
          tileImg: tile5,
          tileHeading: "Своя пекарня",
          tileText:
            "Знак «Печём сами» на карточках товаров означает, что мы привезём вам свежеиспеченный тёплый хлеб.",
        },
        {
          tileImg: tile6,
          tileHeading: "Работаем с 1995 года",
          tileText:
            "Мы занимаемся продуктами с 1995 года — все процессы хранения и доставки отточены до мелочей.",
        },
      ],
    };
  },
  methods: {
    resizeHandler() {
      const tileHeadings = document.querySelectorAll(".tile__heading");

      if (document.documentElement.clientWidth === 320) {
        [...tileHeadings][1].style.marginBottom = "15px";
      } else if (
        document.documentElement.clientWidth > 320 &&
        document.documentElement.clientWidth <= 650
      ) {
        [...tileHeadings][1].style.marginBottom = "40px";
      } else {
        [...tileHeadings][1].style.marginBottom = "55px";
      }
    },
  },
  mounted() {
    this.resizeHandler();
    window.addEventListener("resize", this.resizeHandler);
  },
};
</script>

<style lang="scss" scoped>
.advantages {
  margin-bottom: 100px;
}
.advantages__heading {
  font-weight: 700;
  line-height: 60px;
  font-size: 36px;
  margin-bottom: 41px;
  color: #26303b;
}
.advantages__wrapper {
  margin: 0px auto;
  max-width: 915px;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}

@media only screen and (max-width: 1024px) {
  .advantages {
    margin-bottom: 43px;
  }
}

@media only screen and (max-width: 940px) {
  .advantages__wrapper {
    padding: 0px 125px;
  }
}

@media only screen and (max-width: 910px) {
  .advantages__wrapper {
    padding: 0px;
  }
}

@media only screen and (max-width: 650px) {
  .advantages__heading {
    font-size: 36px;
    line-height: 32px;
    max-width: 250px;
    margin: 0px auto;
    margin-bottom: 24px;
    text-align: center;
  }
}

@media only screen and (max-width: 400px) {
  .advantages__heading {
    font-size: 30px;
  }
}

@media only screen and (max-width: 320px) {
  .advantages {
    margin-bottom: 50px;
  }
  .advantages__heading {
    font-size: 26px;
    line-height: 32px;
    max-width: 185px;
    margin: 0px auto;
    margin-bottom: 24px;
  }
}
</style>
