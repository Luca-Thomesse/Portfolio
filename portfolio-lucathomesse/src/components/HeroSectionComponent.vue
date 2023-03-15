<template>
  <main class="HeroSection">
    <div class="HeroSection__content">
    <div class="HeroSection__description-text">
    <h1 class="HeroSection__title">
      <span class="portfolioTextGradient">{{gradientTitle}}</span>
      <br>
      {{whiteTitle}}
    </h1>
      <p class="HeroSection__text">{{description}}</p>
    </div>
    <div class="HeroSection__description-image">
      <img class="HeroSection__image" :src="image">
    </div>
    </div>
    <div class="HeroSection__banner" v-if="isBannerActive">
      <p class="portfolioTextGradient" v-for="item in items" :key="item">
        {{item}}
      </p>
    </div>

  </main>
</template>
<script>
export default {
  name: 'HeroSectionComponent',
  props: {
    items: {
      type: Object,
      default: () => [
        'photo',
        'communication',
        'vidéo',
        'découvrir',
        'photo',
        'communication',
        'vidéo',
      ]
    },
    gradientTitle: {
      type: String,
      default: 'Gradient title'
    },
    whiteTitle: {
      type: String,
      default: 'White title'
    },
    description: {
      type: String,
      default: 'Description'
    },
    image: {
      type: String,
      default: null
    },
    isBannerActive: {
      type: Boolean,
      default: true
    }
  }
}
</script>

<style lang="scss" scoped>
@import "src/scss/foundations/variable.scss";

.HeroSection__banner {
  padding: 20px 0;
  width: 100vw;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  font-weight: $-fw-l;
  font-size: $-t-m;
  margin-left: -100px;
  margin-top: $-sp-l;
  font-family: $portfolioLogo_font;
  text-transform: uppercase;
  position: relative;
  background-clip: padding-box;
  background-color: white;
  &::before{
    content: '';
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: -1;
    margin: -10px;
    border-radius: inherit;
    background: $portfolioGradientColor_font;
  }
}

.HeroSection__image {
  width: 300px;
  margin-top: $-sp-s;
}

.HeroSection__content {
  display: flex;
  align-items: center;
}

.HeroSection__title {
  margin-top: $-sp-m;
  font-size: $-t-l;
  line-height: $-t-l;
}

.HeroSection__text {
  margin-top: $-sp-xs;
  font-size: $-t-s;
  line-height: $-t-m;
}
</style>