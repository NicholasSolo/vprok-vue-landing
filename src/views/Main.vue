<template>
  <div class="wrapper">
    <Header />
    <ContentSection />
    <Footer />
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import ContentSection from "@/components/ContentSection.vue";
import Footer from "@/components/Footer.vue";

export default {
  name: "Main",
  components: {
    Header,
    ContentSection,
    Footer,
  },
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
.wrapper {
  margin: 0px auto;
  max-width: 1440px;
  background: #e5e5e5;
}
</style>
