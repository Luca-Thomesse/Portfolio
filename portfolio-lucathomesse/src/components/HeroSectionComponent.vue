<template>
  <main class="HeroSection">
    <div class="HeroSection__content">
    <div class="HeroSection__description-text">
    <h1 class="HeroSection__title">
      <span class="portfolioTextGradient">Je suis Luca,</span>
      <br>
      et bienvenue sur mon portefolio
    </h1>
      <p class="HeroSection__text">Découvrez mes projets dans diverses domaines tel que la photographie, la vidéo et la communication.</p>
    </div>
    <div class="HeroSection__description-image">
      <img class="HeroSection__image" src="public/images/moi.png">
    </div>
    </div>
    <div class="HeroSection__banner">
      <p v-for="item in items" :key="item">
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
      type: Array,
      default: () => [
        'photo',
        'communication',
        'vidéo',
        'découvrir',
        'photo',
        'communication',
        'vidéo',
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
@import "src/scss/foundations/variable.scss";

.HeroSection__banner {
  padding: 20px 15px;
  width: 1440px;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  background-color: white;
  color: $portfolioInitialColor_font;
  font-weight: $-fw-m;
  margin-left: -100px;
  margin-top: $-sp-l;
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