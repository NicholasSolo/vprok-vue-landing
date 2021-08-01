<template>
  <div class="tile">
    <div class="img__wrapper">
      <img :src="tile.tileImg" :alt="tile.tileHeading" class="tile__img" />
    </div>
    <p class="tile__heading">{{ tile.tileHeading }}</p>
    <p class="tile__text">{{ tile.tileText }}</p>
  </div>
</template>

<script>
export default {
  name: "AdvantageCard",
  props: {
    tile: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.tile {
  max-width: 285px;
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
.tile:nth-child(3n) {
  margin-right: 0px;
}
.img__wrapper {
  height: 90px;
  margin-bottom: 30px;
}
.tile__heading {
  font-weight: bold;
  margin-bottom: 30px;
}

@media only screen and (max-width: 940px) {
  .tile:nth-child(3n) {
    margin-right: 30px;
  }
  .tile:nth-child(2n) {
    margin-right: 0px;
  }
}

@media only screen and (max-width: 650px) {
  .tile {
    max-width: 175px;
    padding: 17px 5px 13px;
    margin-bottom: 10px;
    margin-right: 9px;
    font-size: 11px;
    line-height: 11px;
  }
  .tile:nth-child(2n) {
    margin-right: 9px;
  }
  .tile:nth-child(3n) {
    margin-right: 0px;
  }
}

@media only screen and (max-width: 542px) {
  .tile:nth-child(3n) {
    margin-right: 10px;
  }
}

@media only screen and (max-width: 320px) {
  .tile {
    max-width: 146px;
    padding: 20px 5px 15px;
    margin-bottom: 10px;
    margin-right: 9px;
    font-size: 8px;
    line-height: 11px;
  }
  .tile:nth-child(3n) {
    margin-right: 9px;
  }
  .tile:nth-child(2n) {
    margin-right: 0px;
  }
  .img__wrapper {
    max-height: 40px;
    margin-bottom: 9px;
    img {
      max-height: 40px;
      max-width: 50px;
    }
  }
  .tile__heading {
    font-weight: bold;
    margin-bottom: 15px;
  }
}
</style>
