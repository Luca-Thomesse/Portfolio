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
    await axios.get('https://portefolio-db.lucathomesse.fr/wp-json/wp/v2/entete/28885').then((response) => {
      this.entete = response.data.acf;
      console.log(this.entete)
    })
  }
}
</script>


<template>

  <div class="VideoView">
    <HeroSectionComponent v-if="entete !== []"
                          :gradient-title="entete.title.gradient"
                          :white-title="entete.title.white"
                          :image="entete.image.url"
                          :description="entete.description"
                          :is-banner-active="true"
                          :items="entete.banner"
    />

    <h2 class="portfolioTextGradient">Les débuts...</h2>
    <p class="text">J’ai commencé à m’intéresser au monde de la vidéo assez jeune en faisant des vidéos sur YouTube avec
      des amis. Puis, au lycée, grâce à mon professeur d’allemand et des camarades, j’ai pu découvrir les courts
      métrages. Depuis, j’ai réalisé un court métrage, participé à une fiction et tourner de nombreuses petites vidéos
      comme un clip de musique.</p>

    <h2 class="portfolioTextGradient">Court métrage</h2>
    <p class="text">Fin 2019, après une discussion avec mon professeur d’allemand et un ami, le projet de réalisé un
      court métrage engagé sur le réchauffement climatique est né. Le projet était, en partenariat avec la société des
      membres de la légion d’honneur (SMLH) et en relation avec Sébastien Drak, pilote d’hélicoptère sur le Polarsterne
      (brise-glace), de réalisé un court métrage humoristique et informatif sur le réchauffement climatique.</p>
    <p class="text">Février 2020, le script est enfin terminé et le tournage peut débuter. Pendant 3 jours, avec une
      équipe de 3 à 6 personnes en fonction des scènes, nous allons faire toutes les captations audio et vidéo pour
      réaliser le court métrage. Mon rôle dans ce projet a été d’organiser le tournage, co-scènariser, co-tourner et
      jouer un des rôles.</p>

    <iframe width="560" height="315" src="https://www.youtube.com/embed/T9nSGlF1uqs" title="YouTube video player"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            allowfullscreen>
    </iframe>

    <p class="text">Après présentation du projet au sein de mon lycée et à la SMLH, nous avons décrocher notre place
      dans l’équipe du lycée pour participer aux Olympiades de la Jeunesse à Paris en Septembre 2021. Ce fût une
      expérience enrichissante et humaine durant cette journée unique à l’HÔTEL NATIONAL DES INVALIDES.</p>

    <h2 class="portfolioTextGradient">Fiction</h2>
    <p class="text">Fin 2020, deux de mes amis qui avaient comme projet de faire des études supérieures dans l’animation
      et le cinéma m’ont proposé de me joindre au projet. Le but était de réaliser une fiction sur la thématique du
      réchauffement climatique et sur les actions pour le contrer qui leur servirait de projet d’entrée pour leurs
      études. </p>
    <p class="text">Le tournage a débuté en février 2021 après 3 mois de préparation et de scénarisation. Le tournage a
      duré 5 jours avec une équipe de 25 personnes dans plusieurs lieux différents. Mon rôle dans ce projet a été
      d’aider à organiser, réaliser le making of, tourner quelques plans annexes et jouer un des rôles.</p>

    <iframe width="560" height="315" src="https://www.youtube.com/embed/rQ3LaphMBmc" title="YouTube video player"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            allowfullscreen></iframe>

    <p class="text">Ce fût une expérience très enrichissante car j’ai pu prendre part à un vrai tournage de style cinéma
      avec une grosse équipe. Ce projet a été récompensé par un prix national et je suis fier d’avoir pu y
      participer.</p>

    <h2 class="portfolioTextGradient">Micro-trottoir</h2>
    <p class="text">En première année de BUT MMI, j'ai pu avoir l'occassion de réaliser lors d'un exercice de cours, un
      tournage de micro-trottoir. Ce projet m'a permis de découvrir les spécificités de ce type de vidéo et d'aquérir des
      compétences techniques. C'était aussi la première fois que je faisais du montage ainsi que du voice over. De ce
      fait, ce micro-trottoir m'a beaucoup apporté.</p>

    <iframe width="560" height="315" src="https://www.youtube.com/embed/WTlxDfrbZFc" title="YouTube video player"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            allowfullscreen></iframe>

    <h2 class="portfolioTextGradient">Montage de vidéo produit</h2>
    <p class="text">Une des nombreuses missions qui me sont données durant mon alternance est le montage vidéo. Je
      réalise des montages de vidéo produits qui sont tournées lors de nos shooting photo. Voici un exemple d'une vidéo
      de présentation de collection</p>

    <iframe width="560" height="315" src="https://www.youtube.com/embed/Iz0ssjtVf70" title="YouTube video player"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            allowfullscreen></iframe>
  </div>


</template>

<style scoped lang="scss">
@import "src/scss/foundations/variable.scss";

.text {
  margin-top: $-sp-xs;
  font-size: $-t-s;
  line-height: $-t-m;
}

iframe {
  display: block;
  margin-right: auto;
  margin-left: auto;
  margin-top: $-sp-s;
  margin-bottom: $-sp-s;

}

</style>