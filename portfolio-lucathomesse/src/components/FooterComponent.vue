<template>
  <div class="footer">
    <navigation/>
    <div class="footer__content">
      <div class="footer__socialMedias">
        <a href=""><img src="/icons/Instagram.png" alt="Instagram" class="footer__icon"></a>
        <a href=""><img src="/icons/LinkedIn.png" alt="LinkedIn" class="footer__icon"></a>
        <a href=""><img src="/icons/YouTube.png" alt="YouTube" class="footer__icon"></a>
      </div>
      <div class="footer__copyright">Luca Thomesse - Tous droits réservés</div>
    </div>
  </div>
</template>

<script>
import Navigation from "@/components/Navigation.vue";

export default {
  name: "FooterComponent",
  components: {Navigation}

}
</script>

<style scoped lang="scss">
@import 'src/scss/foundations/variable.scss';

.footer {
  position: relative;
  background-clip: padding-box;
  background-color: $portfolioBackground;
  &::before {
    content: '';
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: -1;
    margin: -3px 0 0 0;
    border-radius: inherit;
    background: $portfolioGradientColor_font;
  }
 &__content {
   display: flex;
   flex-direction: row-reverse;
   margin: 0 20px 20px 20px;
   justify-content: space-between;
   align-items: end;
 }
  &__socialMedias {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    width: 220px;

 }
  &__icon {
    width: 60px;
    height: auto;
  }
}

</style>