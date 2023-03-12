<template>
<button><slot></slot></button>
</template>

<script>
export default {
  name: "bouton"
}
</script>

<style scoped lang="scss">
@import "src/scss/foundations/variable.scss";
button {
  font-family: $portfolioMainTitle_font;
  padding: 10px 40px;
  font-size: $-t-s;
  color: $portfolioBackground;
  border-radius: 15px;
  border: 2px solid $portfolioBackground;
  background-color: rgba(255,255,255,1);
  transition: all ease-in .3s;
  &:hover {
    background-color: rgba(255,255,255,0);
    border-color: white;
    color: white;
  }
}

</style>