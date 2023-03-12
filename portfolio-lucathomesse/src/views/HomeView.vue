<script setup>
import HeroSectionComponent from "@/components/HeroSectionComponent.vue";
import PortfolioParagraphe from "@/components/PortfolioParagraphe.vue";
import Bouton from "@/components/bouton.vue";
import BigCard from "@/components/bigCard.vue";
import LittleCard from "@/components/littleCard.vue";</script>

<template>
  <div class="HomeView">
    <HeroSectionComponent/>
    <PortfolioParagraphe/>
    <h2 class="portfolioTextGradient">Mes travaux</h2>
    <big-card v-for="item in 3"/>
    <h2 class="portfolioTextGradient">Logiciels</h2>
    <div class="container__littleCard">
      <little-card v-for="item in 5"/>
    </div>




  </div>
</template>

<style scoped lang="scss">
.container__littleCard {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;

}
</style>


