<script>
import HeroSectionComponent from "@/components/HeroSectionComponent.vue";
import PortfolioParagraphe from "@/components/PortfolioParagraphe.vue";
import BigCard from "@/components/bigCard.vue";
import LittleCard from "@/components/littleCard.vue";
import axios from "axios";
import bigCard from "@/components/bigCard.vue";
import littleCard from "@/components/littleCard.vue";

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "homepage",
  computed: {
    littleCard() {
      return littleCard
    },
    bigCard() {
      return bigCard
    }
  },
  components: {
    HeroSectionComponent,
    PortfolioParagraphe,
    BigCard,
    LittleCard,
  },
  data() {
    return {
      entete: [],
      bigcards: [],
      littlecards: [],
    }
  },
  async created() {
    await axios.get('https://portefolio-db.lucathomesse.fr/wp-json/wp/v2/entete/28848').then((response) => {
      this.entete = response.data.acf;
      console.log(this.entete);
    })
    await axios.get('https://portefolio-db.lucathomesse.fr/wp-json/wp/v2/bigcard').then((response) => {
      this.bigcards = response.data;
      console.log(this.bigcards);
    })
    await axios.get('https://portefolio-db.lucathomesse.fr/wp-json/wp/v2/littlecard').then((response) => {
      this.littlecards = response.data;
      console.log(this.littlecards);
    })
  }
}
</script>

<template>
  <div class="HomeView">
    <HeroSectionComponent v-if="entete !== []"
                          :gradient-title="entete.title.gradient"
                          :white-title="entete.title.white"
                          :image="entete.image.url"
                          :description="entete.description"
                          :items="entete.banner"
                          :is-banner-active="true"
    />

    <h2 class="portfolioTextGradient">Qui suis je ?</h2>
    <p class="text">Je suis Luca Thomesse, jeune homme de 19 ans passionné par les métiers du multimédia depuis petit.
      J’ai débuté par faire des photos lors de projets artistiques pour mes cours d’art. Puis, avec des amis, j’ai
      commencé à réaliser des courts métrages quand j’étais au lycée. S’en est suivi la captation photo et vidéo
      d’événements tel qu’un mariage ou encore des événements étudiants. Étant en 2ème année de BUT Métiers du
      Multimédia et de l’Internet, j’ai pu en apprendre davantage sur les métiers du multimédia et parfaire mes
      connaissances lors de projets. Je suis également en alternance depuis septembre 2022 et je découvre en quoi mes
      réalisations sont utiles dans le monde du travail.</p>

    <h2 class="portfolioTextGradient">Mes travaux</h2>
    <template v-for="bigCard in bigcards" :key="bigCard.id">
      <big-card
          :image-link="bigCard.acf.image"
          :title="bigCard.acf.title"
          :link="bigCard.acf.link"
      />
    </template>

    <h2 class="portfolioTextGradient">Logiciels</h2>
    <div class="container__littleCard">
      <template v-for="littlecard in littlecards" :key="littlecard.id">
        <little-card class="littleCard"
                     :icon-link="littlecard.acf.image"
                     :title="littlecard.acf.title"
        />
      </template>
    </div>
  </div>
</template>

<style scoped lang="scss">
.container__littleCard {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;

}

.littleCard {
  &__icon-link {
    width: 126px;
    height: auto;
  }
}
</style>


