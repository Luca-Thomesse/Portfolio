<template>


  <div class="PhotoView">
    <HeroSectionComponent v-if="entete !== []"
                          :gradient-title="entete.title.gradient"
                          :white-title="entete.title.white"
                          :image="entete.image.url"
                          :description="entete.description"
                          :is-banner-active="true"
                          :items="entete.banner"
    />

    <h2 class="portfolioTextGradient">Les débuts...</h2>
    <p class="text">J’ai toujours été passionné par les métiers de l’image et la photographie depuis que je suis petit.
      J’ai commencé par faire des photos avec mon téléphone comme tout le monde. Puis, début 2020, j’ai acheté mon
      premier appareil photo et depuis je ne me suis jamais arrêté. Entre évenements, architecture, animalier ou encore
      astrophoto, j’ai pu découvrir un grand nombre de personnes et la beauté de notre monde grâce à la
      photographie.</p>

    <h2 class="portfolioTextGradient">Événements</h2>

    <h3>Mariage</h3>
    <p class="text">J’ai eu la chance, le 3 juillet 2021, de capturer un moment de vie très important pour de très
      nombreuses personnes : un mariage. Cette expérience fût très stressante et professionnalisante pour moi compte
      tenu de l’importance de prendre des clichés réussis.</p>
    <div class="image">
      <img class="item" src="public/images/PSX_20210730_113828.jpg">
      <img class="item" src="public/images/PSX_20210730_120246.jpg">
      <img class="item" src="public/images/PSX_20210801_160428.jpg">
    </div>

    <h3>Concerts</h3>
    <p class="text">J’ai pu, à plusieurs reprises, avoir l’opportunité de photographier des concerts en 2021. L’un dans
      la cour d’une auberge restaurant en Alsace où un duo de jeunes musiciens se produisait. Puis le second étant un
      festival de Jazz dans la cour du château des Capucins dans les Vosges.</p>
    <div class="image">
      <img class="item" src="public/images/PSX_20210805_222210.jpg">
      <img class="item" src="public/images/20210730192304_IMG_8595.JPG">
      <img class="item" src="public/images/20210619192211_IMG_6538.JPG">
    </div>

    <h3>Événements étudiants</h3>
    <p class="text">Faisant partie de plusieurs associations étudiantes en tant que photographe et organisateur
      événementiel depuis septembre 2021, j’ai pu photographier de nombreux événements. Entre intégration, nuits
      sportives ou encore soirée étudiantes, j’ai pu découvrir et approfondir mes compétences en photographie
      événementielle.</p>
    <div class="image">
      <img class="item" src="public/images/24052022-IMG_2695.jpg">
      <img class="item" src="public/images/06102022-IMG_3901.jpg">
      <img class="item" src="public/images/24052022-IMG_2435.jpg">
    </div>

    <h2 class="portfolioTextGradient">Animalier</h2>

    <p class="text">Je me suis essayé à la photographie animalière et j’ai pu capturer des instants uniques de la
      faune.</p>
    <div class="image">
      <img class="item" src="public/images/20201028111605_IMG_9837.JPG">
      <img class="item" src="public/images/PSX_20200702_112350.jpg">
      <img class="item" src="public/images/PSX_20201028_133845.jpg">
    </div>

    <h2 class="portfolioTextGradient">Dystopian Forest</h2>

    <p class="text">Voici un exemple de série photographique que je réalise. Ici, je vous présente "Dystopian Forest"
      qui met en
      avant la beauté des forêts vosgiennes entre brûme et épineux.</p>
    <div class="image">
      <img class="item" src="public/images/PSX_20200613_193852.jpg">
      <img class="item" src="public/images/IMG_20200601_103536_806.jpg">
      <img class="item" src="public/images/PSX_20200710_091755.jpg">
    </div>

    <h2 class="portfolioTextGradient">Architecture</h2>

    <p class="text">J’ai parcouru différents espaces urbain à la recherche de formes, de lignes et de structures
      intéressantes. J’ai
      réalisé des clichés d’architectures uniques qui montrent la technicité et la grandeur des bâtiments de nos
      villes.</p>
    <div class="image">
      <img class="item" src="public/images/1618656254133.jpg">
      <img class="item" src="public/images/PSX_20201027_124955.jpg">
      <img class="item" src="public/images/PSX_20210417_110522.jpg">
    </div>

    <h2 class="portfolioTextGradient">Travail et recherches artistiques</h2>

    <p class="text">Ayant été en spécialité art plastique au lycée et intéressé par l’art depuis tout petit, j’ai
      réalisé quelques projets photographiques artistiques. Entre travailler le flou, la macro photographie ou le contre
      jour, la photographie regorge de techniques pour exprimer son trait artistique.</p>
    <div class="image">
      <img class="item" src="public/images/PSX_20200801_080646.jpg">
      <img class="item" src="public/images/PSX_20210328_160204.jpg">
      <img class="item" src="public/images/PSX_20210314_115448.jpg">
    </div>
    <div class="image">
      <img class="item" src="public/images/PSX_20201202_143710.jpg">
      <img class="item" src="public/images/PSX_20210216_121210.jpg">
      <img class="item" src="public/images/PSX_20210606_223341.jpg">
    </div>

    <h2 class="title">Et bien d'autres clichés à découvrir sur mes réseaux.</h2>


  </div>

</template>

<script>
import HeroSectionComponent from "@/components/HeroSectionComponent.vue";
import axios from "axios";

export default {
  name: "photopage",
  components: {
    HeroSectionComponent,
  },
  data() {
    return {
      entete: [],
    }
  },
  async created() {
    await axios.get('https://portefolio-db.lucathomesse.fr/wp-json/wp/v2/entete/28877').then((response) => {
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

.title {
  text-align: center;
}

</style>