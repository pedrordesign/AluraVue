<template>
  <md-app>
    <md-app-toolbar class=" main-header md-theme-default md-elevation-2 md-elevation-2">
      <div class="md-toolbar-section-start">
        <md-button class="md-icon-button" @click="menuVisible = !menuVisible">
          <md-icon>menu</md-icon>
        </md-button>
        <span class="md-title">
          <h1>{{title}}{{menuVisible}}</h1>
        </span>
      </div>
      <div class="md-toolbar-section-end">
        <div class="md-layout md-gutter">
          <div class="md-layout-item">
            <md-field>
              <label>{{searchLabelTitle}}</label>
              <md-input v-model="search"></md-input>
            </md-field>
          </div>
        </div>
      </div>
    </md-app-toolbar>
  <md-app-drawer :md-active.sync="menuVisible">
    <pageMenu></pageMenu>
  </md-app-drawer>
    <md-app-content>
      <span>{{search}}</span>
      <div class="md-content demo md-theme-demo-light">
        <div class="demo-content">
          <div class="md-layout">
            <div v-for="img of filteredImgs" class="md-layout-item md-medium-size-30 md-small-size-50 md-xsmall-size-90">
              <painel :titulo="img.titulo">
                <imgresponsive :url="img.url" :title="img.titulo"> </imgresponsive>
              </painel>
            </div>
          </div>
        </div>
      </div>
    </md-app-content>
  </md-app>
</template>

<script>

import Search from './shared/Search.vue';
import Painel from './shared/painel/Painel.vue';
import ImgResponsive from './shared/ImgResponsive.vue';
import Menu from './shared/Menu.vue';

export default {

  components: {
    painel: Painel,
    search: Search,
    imgresponsive: ImgResponsive,
    pageMenu: Menu
  },
  data () {
    return{
      title: 'Teste',
      searchLabelTitle: 'Search',
      search: '',
      imgs: [],
      menuVisible: false
    }
  },

  computed: {

    filteredImgs() {
      if(this.search) {
        let exp = new RegExp(this.search.trim(), 'i');
        return this.imgs.filter(img => exp.test(img.titulo))
        return[];
      }else{
        return this.imgs;
      }
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
