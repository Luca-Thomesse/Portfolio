<template>
  <div class="ComView">

    <HeroSectionComponent v-if="entete !== []" :gradient-title="entete.title.gradient" :white-title="entete.title.white"
      :image="entete.image.url" :description="entete.description" :is-banner-active="true" :items="entete.banner" />

    <h2 class="portfolioTextGradient">Les débuts...</h2>
    <p class="text">J’ai commencé la communication lors de mes études en BUT Métiers du Multimédia et de l’Internet en
      2021. À présent, je suis en deuxième année et en alternance en tant qu’Assistant Marketing. J’ai réalisé de
      nombreux dossier de communication, création de visuels pour le web et pour l’impression.</p>

    <h2 class="portfolioTextGradient">BUT MMI</h2>
    <p class="text">Mes études en BUT Métiers du Multimédia et de l'Internet m'ont beaucoup apporté dans le domaine de
      la communication. En deuxième année, j'ai décidé de suivre la spécialité communication. Voici quelques réalisations
      dans le domaine de la communication que j'ai réalisé lors de mes études.</p>

    <h3>Dossier de communication</h3>
    <p class="text">J'ai eu à plusieurs reprises le devoir de réaliser des dossiers de communication et d'étude
      préalable. Dans ce type dossier, nous allons retrouver un grand nombre de catégories de recherches. On peut
      retrouver une analyse technique qui montre les technologies, logiciels et éléments nécessaires à la mise en place
      du projet. On peut également retrouver une analyse stratégique qui va permettre de montrer le ciblage, l'étude
      de concurrence etc. Un dossier est quelque chose de très complet qui permet de justifier de la pertinence du
      projet et de la faisabilité de sa réalisation. </p>
    <div class="image">
      <img class="item" src="../assets/BOTH.jpg">
      <img class="item" src="../assets/FRONT.jpg">
    </div>
    <p class="text">Ce projet a été une réelle expérience pour moi par le domaine qu'il aborde. Le projet de 3ème
      semestre portait sur les NFT, un domaine que je ne connaissais pas. De ce fait, il a fallu beaucoup se renseigner
      pour préparer un dossier de faisabilité le plus réel possible. Étant chef de projet, j'ai du en simultaner,
      préparer le dossier et faire de la gestion de projet avec Trello et un diagramme de GANTT.</p>

    <h3>Création print & web</h3>
    <p class="text">J'ai du réalisé différentes créations web ou print lors de mon BUT MMI. De la maquette d'interface à
      la création de cartes postales et passant par la création de logos, la formation MMI regorge de projet de création
      print et web.</p>
    <div class="image">
      <img class="item" src="../assets/DESIGN4.png">
      <img class="item" src="../assets/Cassandre.png">
      <img class="item" src="../assets/Maquette.png">
    </div>

    <h2 class="portfolioTextGradient">Alternance - Assistant marketing</h2>
    <p class="text">Grâce à ma formation, j'ai pu accéder à la formation en alternance à partir de ma deuxième année de
      BUT MMI. Je suis donc assistant marketing dans une entreprise de textile dans le service marketing. Mes missions
      sont de réaliser des visuels de communication web et print ainsi que le montage de vidéos produits, la photo à plat
      de produits et un peu de manutention.
      <br> De ce fait, j'ai eu notamment l'opportunité de réaliser des cartes
      postales ou encore une Newsletter.
    </p>

    <div class="image">
      <img class="item" src="../assets/FicheProduit.png">
      <img class="item" src="../assets/FRONT.png">
      <img class="item" src="../assets/BACK.png">
    </div>

    <div class="image">
      <img class="items" src="../assets/N-Part1.png">
      <img class="items" src="../assets/N-Part2.png">
      <img class="item" src="../assets/Signature.jpg">
    </div>



  </div>
</template>

<script>
import HeroSectionComponent from "@/components/HeroSectionComponent.vue";
import axios from "axios";

export default {
  name: "videopage",
  components: {
    HeroSectionComponent,
  },
  data() {
    return {
      entete: [],
    }
  },
  async created() {
    await axios.get('https://portefolio-db.lucathomesse.fr/wp-json/wp/v2/entete/28887').then((response) => {
      this.entete = response.data.acf;
      console.log(this.entete)
    })
  }
}
</script>

<style scoped lang="scss">
@import "src/scss/foundations/variable.scss";

.text {
  margin-top: $-sp-xs;
  font-size: $-t-s;
  line-height: $-t-m;
}

.image {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  margin-top: $-sp-s;
  margin-bottom: $-sp-s;
}

.item {
  max-width: auto;
  max-height: 300px;
}

.items {
  max-width: auto;
  max-height: 500px;
}

h3 {
  margin-top: $-sp-s;
}
</style>

