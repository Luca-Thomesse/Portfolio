<template>
  <div class="headerComponent">
    <RouterLink class="headerComponent__logo portfolioLogo" to="/">Lutho</RouterLink>
    <nav class="headerComponent__nav" @click="burgerMenu()">
      <RouterLink class="headerComponent__nav-item" to="/photo">Photo</RouterLink>
      <RouterLink class="headerComponent__nav-item" to="/video">Video</RouterLink>
      <RouterLink class="headerComponent__nav-item" to="/communication">Communication</RouterLink>
      <RouterLink class="headerComponent__nav-item" to="/contact">Contact</RouterLink>
    </nav>
    <div class="headerComponent__menu-burger" @click="burgerMenu()"/>
  </div>
</template>
<script>
export default {
  name: 'headerComponent',
  methods: {
    toggleMenu() {
      const nav = document.querySelector('.headerComponent__nav');
      nav.classList.toggle('active');
    },
    burgerMenu() {
      const burger = document.querySelector('.headerComponent__menu-burger');
      burger.classList.toggle('open');
      this.toggleMenu()
    },
  },
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
    @media (max-width: 768px) {
      flex-direction: column;
      justify-content: center;
      width: 100vw;
      height: 100vh;
      background-color: white;
      position: fixed;
      top: 0;
      left: 0;
      transform: translateX(100vw);
      transition: transform 0.5s ease-in-out;
    }
  }

  &__nav-item {
    font-size: $-t-s;
    font-weight: $-fw-s;
    @media (max-width: 768px) {
      color: $portfolioInitialColor_font;
      font-size: $-t-m;
      margin-bottom: 30px;
    }
  }
  &__menu-burger {
    width: 40px;
    height: 6px;
    border-radius: 8px;
    background: $portfolioGradientColor_font;
    position: absolute;
    z-index: 100;
    top: 35px;
    right: 30px;
    transition: all 0.5s ease-in-out;
    &::before {
      content: "";
      width: 40px;
      height: 6px;
      border-radius: 8px;
      background: $portfolioGradientColor_font;
      display: block;
      transform: translateY(-14px) translateX(10px);
      transition: transform 0.5s ease-in-out;
    }
    &::after {
      content: "";
      width: 40px;
      height: 6px;
      border-radius: 8px;
      background: $portfolioGradientColor_font;
      display: block;
      transform: translateY(7px) translateX(-10px) rotate(180deg);
      transition: transform 0.5s ease-in-out;
    }
    @media (min-width: 768px) {
      display: none;
    }
  }
}




</style>