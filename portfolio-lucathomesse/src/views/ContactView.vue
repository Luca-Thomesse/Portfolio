<template>


  <div class="HomeView">
    <HeroSectionComponent v-if="entete !== []"
                          :gradient-title="entete.title.gradient"
                          :white-title="entete.title.white"
                          :image="entete.image.url"
                          :description="entete.description"
                          :is-banner-active="false"
    />

    <contact/>


  </div>

</template>

<script>
import HeroSectionComponent from "@/components/HeroSectionComponent.vue";
import axios from "axios";
import Contact from "@/components/Contact.vue";

export default {
  name: "contactpage",
  components: {
    Contact,
    HeroSectionComponent,
  },
  data() {
    return {
      entete: [],
    }
  },
  async created() {
    await axios.get('https://portefolio-db.lucathomesse.fr/wp-json/wp/v2/entete/28851').then((response) => {
      this.entete = response.data.acf;
      console.log(this.entete)
    })
  }
}

</script>