<template>
  <v-container>
    <v-row>
      <!-- 画像のリストを表示 -->
      <v-col
        v-for="(image, index) in images"
        :key="index"
        cols="12" sm="4" md="3"
      >
        <v-card @click="openDialog(image)">
          <v-img :src="image.url" :alt="image.alt" height="200px"></v-img>
          <v-card-title>{{ image.title }}</v-card-title>
        </v-card>
      </v-col>
    </v-row>

    <!-- 画像拡大表示用のダイアログ -->
    <v-dialog v-model="dialog" max-width="800px">
      <v-img :src="dialogImage.url" :alt="dialogImage.alt"></v-img>
    </v-dialog>
  </v-container>
</template>

<script>
export default {
  name: "Gallery",
  data() {
    return {
      dialog: false,  // ダイアログの表示状態
      dialogImage: {},  // 拡大表示する画像のデータ
      images: [
        {
          url: require('@/assets/sample01.png'),
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
  },
  methods: {
    // ダイアログを開いてクリックされた画像をセット
    openDialog(image) {
      this.dialogImage = image;
      this.dialog = true;
    }
  }
};
</script>

<style scoped>
/* ギャラリーのスタイル */
.v-card {
  cursor: pointer;
  margin-bottom: 20px;
}
</style>
