<template>
    <md-app>
      <md-app-toolbar class=" main-header md-theme-default md-elevation-2 md-elevation-2">
        <div class="md-toolbar-section-start">
          <h1>{{title}}</h1>
        </div>
        <div class="md-toolbar-section-end">
          <search :searchLabelTitle="searchLabelTitle" ></search>
        </div>
      </md-app-toolbar>
      <md-app-content>
        <span>{{search}}</span>
        <painel :imgs="imgs"></painel>
      </md-app-content>
    </md-app>
</template>

<script>

import Search from './shared/painel/Search.vue';
import Painel from './shared/painel/Painel.vue';

export default {

  components: {
    painel: Painel,
    search: Search
  },
  data () {
    return{
      title: "Teste",
      searchLabelTitle: "Search",
      imgs: []
    }
  },
  created () {
    let promise = this.$http.get('http://localhost:3000/v1/fotos')

    promise
      .then(res => res.json(0))
      .then(rj => {
        this.imgs = rj
      },
      err => {
        console.log(err)
      }
      )
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
