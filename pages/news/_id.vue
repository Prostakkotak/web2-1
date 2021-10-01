<template>
  <v-row class="d-flex flex-column col-xs-12 col-sm-10 col-md-8 px-4">
    <v-btn class="caption mb-4" to="/news">&lt; - вернуться</v-btn>
    <h1>Заголовок новости</h1>
    <p></p>
    <p class="caption">21.12.2021</p>
  </v-row>
</template>

<script>
export default {
  computed: {
    ...mapGetters({
      getNews: "news/getNewsList",
    }),
  },
};
</script>