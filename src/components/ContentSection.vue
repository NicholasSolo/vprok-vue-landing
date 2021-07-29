<template>
  <section class="main">
    <Advantages />
    <Carousel />
    <Bonus />
  </section>
</template>

<script>
import Advantages from "@/components/Advantages.vue";
import Carousel from "@/components/Carousel.vue";
import Bonus from "@/components/Bonus.vue";

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
