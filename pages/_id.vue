<template>
  <v-row class="d-flex flex-column col-xs-12 col-sm-10 col-md-8 px-4">
    <v-btn class="caption mb-4" to="/newspage">&lt; - вернуться</v-btn>
    <h1>{{this.newsData.name}}</h1>
    <p>{{this.newsData.desc}}</p>
    <p class="caption">{{this.newsData.date}}</p>
  </v-row>
</template>

<script>
export default {
  data: () => ({
    newsData: "",
  }),
  async asyncData({ params }) {
    const id = params.id;
    return { id };
  },
  mounted() {
    this.$store.state.news.newsList.find((e) => {
      if (e.id == this.id) {
        this.newsData = e
      }
    });
  },
}
</script>