<script setup>

import AppFooter from './components/AppFooter.vue';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

</script>

<template>

  <AppHeader/>
  <AppMain/>
  <AppFooter/>

</template>

<style lang="scss">

@use'./styles/general.scss' as *;
@use'./styles/partials/mixin' as *;
@use'./styles/partials/variants' as *;

</style>
