<template>
  <div>
    <ul class="news-list">
      <li v-for="item in this.$store.state.news" class="news-list__post">
        <div class="news-list__point">
          {{ item.points }}
        </div>
        <div class="news-list__content">
          <a v-bind:href="item.url"
            ><h3 class="news-list__content__title">{{ item.title }}</h3>
          </a>
          <small>
            {{ item.time_ago }} by
            <router-link class="router_a" v-bind:to="`user/${item.user}`">{{ item.user }} </router-link>
          </small>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
import { fetchNewsList } from "../api/index.js";

export default {
  computed: {
    //...mapGetters([
    //  'fetchedNews'
    //])
    //   newsItems :'fetchedNews'
    //})
    //#3
    //...mapGetters({
    //   newsItems :'fetchedNews'
    //})
    //#2
    //...mapState({
    //  news : state => state.news
    //})
    //#1
    //ask(){
    //  return this.s$$store.state.ask;
    //}
  },
  created() {
    this.$store.dispatch("FETCH_NEWS");
  },
};
</script>

<style>
</style>
