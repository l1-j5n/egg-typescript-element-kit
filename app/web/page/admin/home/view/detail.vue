<template>
  <div style="font-size: 24px; text-align: center">
    vue-server-render detail <router-link to="/article/add">Add</router-link>
    <img src="../../../../asset/images/egg-vue-webpack-dev.png"/>
  </div>
</template>
<style>

</style>
<script type="ts">
  export default {
    preFetch({ state, dispatch, commit }) {
      let { id } = state.route.params;
      return Promise.all([
        dispatch('FETCH_ARTICLE_DETAIL', { id })
      ]);
    },
    beforeMount() {
      let { id } = this.$store.state.route.params;
      return Promise.all([
        this.$store.dispatch('FETCH_ARTICLE_DETAIL', { id })
      ]);
    }
  }
</script>
