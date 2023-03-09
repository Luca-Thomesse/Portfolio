<template>
  <div class="headerComponent">
    <RouterLink class="headerComponent__logo portfolioLogo" to="/">Lutho</RouterLink>
    <nav class="headerComponent__nav">
      <RouterLink class="headerComponent__nav-item" to="/photo">Photo</RouterLink>
      <RouterLink class="headerComponent__nav-item" to="/video">Video</RouterLink>
      <RouterLink class="headerComponent__nav-item" to="/communication">Communication</RouterLink>
      <RouterLink class="headerComponent__nav-item" to="/contact">Contact</RouterLink>
    </nav>
  </div>
</template>
<script>
export default {
  name: 'headerComponent'
}
</script>

<style lang="scss" scoped>
@import "src/scss/foundations/variable.scss";

.headerComponent {
  padding: 10px 24px;
  display: flex;
  justify-content: space-between;
  &__logo {
color: $portfolioSecondaryColor_font;
text-decoration: underline;
font-size: $-t-logo;
    text-transform: uppercase;
  }
  &__nav {
width: 500px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }
  &__nav-item {
    font-size: $-t-s;
    font-weight: $-fw-s;
  }
}




</style>