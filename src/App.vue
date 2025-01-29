<template>
  <v-app>
    <v-container>
      <h1 class="text-center">画像ギャラリー</h1>
      <Gallery />
    </v-container>
  </v-app>
</template>

<script>
import Gallery from './components/Gallery.vue';

export default {
  name: 'App',
  components: {
    Gallery
  }
};
</script>

<style>
/* アプリ全体のスタイル */
.v-container {
  margin-top: 20px;
}
</style>
