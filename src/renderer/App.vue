<template>
  <div id="app">
    <layout-header></layout-header>
    <router-view></router-view>
  </div>
</template>

<script>
import LayoutHeader from './components/Layout/Header';

export default {
  name: 'App',
  components: {
    LayoutHeader,
  },
};
</script>

<style lang="scss" src="./styles/main.scss" />
