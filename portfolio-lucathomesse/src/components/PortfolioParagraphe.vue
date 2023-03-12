<template>
  <h2 class="portfolioTextGradient">{{title}}</h2>
  <h3 v-if="subtitle">{{subtitle}}</h3>
  <p class="text">{{text}}</p>
</template>
<script>
export default {
  name: 'PortfolioParagraphe',
  props: {
    title: {
      type: String,
      default: 'Qui suis-je ?'
    },
    subtitle: {
      type: String,
      default: null,
    },
    text: {
      type: String,
      default: 'Je suis Luca Thomesse, jeune homme de 19 ans passionné par les métiers du multimédia depuis petit. J’ai débuté\n' +
          '    par faire des photos lors de projets artistique pour mes cours d’art. Puis, avec des amis, j’ai commencé à\n' +
          '    réaliser des courts métrages quand j’étais au lycée. S’en est suivi la captation photo et vidéo d’événements tel\n' +
          '    qu’un mariage ou encore des événements étudiants. Etant en 2ème année de BUT Métiers du Multimédia et de\n' +
          '    l’Internet, j’ai pu en apprendre davantage sur les métiers du multimédia et parfaire mes connaissances lors de\n' +
          '    projets.'
    }
  }
}
</script>

<style scoped lang="scss">



</style>