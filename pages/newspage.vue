<template>
  <v-row>
    <v-list class="d-flex flex-column col-xs-12 col-sm-10 col-md-8 px-4">
      <v-hover v-slot="{ hover }" v-for="news in getNews" :key="news.id">
        <NuxtLink :to="`news/${news.id}`">
        <v-card
          :elevation="hover ? 12 : 2"
          :class="{ 'on-hover': hover, 'pa-4 ma-2 col': true }"
        >
          <h2>{{ news.name }}</h2>
          <p
            style="
              max-width: 70ch;
              overflow: hidden;
              white-space: nowrap;
            "
          >
            {{ news.desc }}
          </p>
          <p>{{ news.date }}</p>
        </v-card>
        </NuxtLink>
      </v-hover>
    </v-list>
  </v-row>
</template>

<script>
import { mapGetters } from "vuex";
export default {
  computed: {
    ...mapGetters({
      getNews: "news/getNewsList",
    }),
  },
};
</script>

<style lang="scss">
.on-hover {
  cursor: pointer;
  transform: scale(1.003);
  transition: 200ms;
}
</style>