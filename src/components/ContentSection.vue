<template>
  <section class="main">
    <Advantages />
    <Carousel />
    <Bonus />
  </section>
</template>

<script>
import Advantages from "./Advantages.vue";
import Carousel from "./Carousel.vue";
import Bonus from "./Bonus.vue";

export default {
  name: "ContentSection",
  components: {
    Advantages,
    Carousel,
    Bonus,
  },
};
</script>

<style lang="scss" scoped></style>
