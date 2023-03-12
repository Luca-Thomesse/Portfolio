<template>
  <navigation/>
</template>
<script>
import Navigation from "@/components/Navigation.vue";

export default {
  name: 'headerComponent',
  components: {Navigation},
}
</script>

<style lang="scss" scoped>
@import "src/scss/foundations/variable.scss";

.active {
  transform: translate(0) !important;
}

.open {
  &::before {
    transform: translateY(-14px) translateX(-10px) !important;
  }
  &::after {
    transform: translateY(7px) translateX(10px) rotate(180deg) !important;
  }
}


</style>