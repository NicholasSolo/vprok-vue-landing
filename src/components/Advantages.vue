<template>
  <div class="advantages">
    <h1 class="advanatges__heading">Преимущества</h1>
    <div class="advantages__wrapper">
      <div class="tile" v-for="item in advantagesTiles" :key="item.id">
        <div class="img__wrapper">
          <img :src="item.tileImg" :alt="item.tileHeading" class="tile__img" />
        </div>
        <p class="tile__heading">{{ item.tileHeading }}</p>
        <p class="tile__text">{{ item.tileText }}</p>
      </div>
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

export default {
  name: "Advantages",
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
  mounted() {
    const headings = document.querySelectorAll(".tile__heading");
    [...headings][1].style.marginBottom = "55px";
  },
};
</script>

<style lang="scss" scoped>
.advantages {
  border: 2px solid pink;
  margin-bottom: 100px;
}
.advanatges__heading {
  font-weight: 700;
  line-height: 60px;
  font-size: 36px;
  margin-bottom: 41px;
  color: #26303b;
}
.advantages__wrapper {
  margin: 0px auto;
  max-width: 945px;
  display: flex;
  flex-wrap: wrap;
}

.tile {
  width: 285px;
  padding: 28px 22px 20px;
  margin-bottom: 30px;
  margin-right: 30px;
  border-radius: 10px;
  background-color: white;
  display: flex;
  flex-direction: column;
  align-items: center;
  font-size: 16px;
  line-height: 24px;
}
.img__wrapper {
  height: 90px;
  margin-bottom: 30px;
}
.tile__heading {
  font-weight: bold;
  margin-bottom: 30px;
}
</style>
