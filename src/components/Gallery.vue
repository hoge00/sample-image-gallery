<template>
    <v-container>
      <v-row>
        <!-- 画像のリストを表示 -->
        <v-col
          v-for="(image, index) in images"
          :key="index"
          cols="12" sm="4" md="3"
        >
          <v-card>
            <v-img :src="image.url" :alt="image.alt" height="200px"></v-img>
            <v-card-title>{{ image.title }}</v-card-title>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  <script>
  export default {
    name: "Gallery",
    data() {
      return {
        images: [
          {
            url: require('@/assets/sample01.png'), // 相対パスを require() でインポート
            alt: "画像1",
            title: "画像タイトル1"
          },
          {
            url: require('@/assets/sample02.png'),
            alt: "画像2",
            title: "画像タイトル2"
          },
          {
            url: require('@/assets/sample03.png'),
            alt: "画像3",
            title: "画像タイトル3"
          },
          {
            url: require('@/assets/sample04.png'),
            alt: "画像4",
            title: "画像タイトル4"
          },
          {
            url: require('@/assets/sample05.png'),
            alt: "画像5",
            title: "画像タイトル5"
          }
        ]
      };
    }
  };
  </script>
  
  <style scoped>
  /* ギャラリーのスタイル */
  .v-card {
    margin-bottom: 20px;
  }
  </style>
  