<template>
  <div class="bigCard">
    <div class="bigCard__image">
      <img :src="imageLink" :alt="imageAlt">
    </div>
    <div class="bigCard__title">
      <h4>{{title}}</h4>
    </div>
    <RouterLink class="bigCard__bouton" :to="link">
      <bouton>Voir plus</bouton>
    </RouterLink>
  </div>

  <!--TODO:  Mettre un routeur link-->


</template>

<script>
import Bouton from "@/components/bouton.vue";

export default {
  name: "bigCard",
  components: {Bouton},
  props: {
    imageLink: {
      type: String,
      default: 'https://images.unsplash.com/photo-1531804055935-76f44d7c3621?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=388&q=80'
    },
    imageAlt: {
      type: String,
      default: 'Une montagne'
    },
    title: {
      type: String,
      default: 'Photo'
    },
    link: {
      type: String,
      default: '/'
    }
  }
}
</script>

<style lang="scss" scoped>
@import "src/scss/foundations/variable.scss";

.bigCard {
  display: flex;
  flex-direction: column;
  margin-bottom: $-sp-m;
  &__image {
    width: 100%;
    height: 460px;
    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
   }
  &__title {
    font-family: $portfolioMainTitle_font;
    color: white;
    font-size: $-t-l;
    background: $portfolioGradientColor_font;
    text-align: center;
    text-transform: uppercase;
  }
  &__bouton {
    margin-left: auto;
    margin-right: auto;
    margin-top: $-sp-s;
  }
}

</style>