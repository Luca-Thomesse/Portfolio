<template>
<div class="littleCard">
  <div class="littleCard__icon">
    <img :src="iconLink" :alt="iconAlt">
  </div>
  <div class="littleCard__title">
    <h5>{{title}}</h5>
  </div>
</div>
</template>

<script>
export default {
  name: "littleCard",
  props: {
    iconLink: {
      type: String,
      default: 'https://upload.wikimedia.org/wikipedia/commons/a/af/Adobe_Photoshop_CC_icon.svg'
    },
    iconAlt: {
      type: String,
      default: 'Icon Photoshop'
    },
    title: {
      type: String,
      default: 'Suite Microsoft 365'
    }
  }

}
</script>

<style lang="scss" scoped>
@import "src/scss/foundations/variable.scss";

.littleCard {
  width: 190px;
  height: 210px;
  background-color: $portfolioInitialColor_font;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-bottom: $-sp-s;
  &__icon {
    img {
      width: auto;
      height: 126px;
    }
    margin-bottom: $-sp-xs;
  }
  &__title {
    font-family: $portfolioMainTitle_font;
    font-size: $-t-s;
  }
}

</style>