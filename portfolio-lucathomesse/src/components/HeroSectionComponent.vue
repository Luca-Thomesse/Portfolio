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
        'découvrir'
      ]
    }
  }
}
</script>