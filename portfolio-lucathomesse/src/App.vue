<script setup>
import {RouterView} from 'vue-router'
import HeaderComponent from "@/components/HeaderComponent.vue";
import FooterComponent from "@/components/FooterComponent.vue";</script>

<template>
  <div class="app">
    <header>
      <headerComponent/>
    </header>

    <RouterView class="app__content"/>
    <footer-component/>
  </div>
</template>

<style lang="scss" scoped>
.app {
  max-width: 1440px;
  margin: 0 auto;

  &__content {
    margin: 0 100px;
  }
}
</style>

