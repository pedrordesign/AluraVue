<template>
  <md-app>
    <md-app-toolbar class=" main-header md-theme-default md-elevation-2 md-elevation-2">
      <div class="md-toolbar-section-start">
        <md-button class="md-icon-button" @click="menuVisible = !menuVisible">
          <md-icon>menu</md-icon>
        </md-button>
        <h1>{{title}}</h1>
      </div>
      <div class="md-toolbar-section-end">
        
      </div>
    </md-app-toolbar>
    <md-app-drawer :md-active.sync="menuVisible">
      <pageMenu></pageMenu>
    </md-app-drawer>
    <md-app-content>
      <div class="md-content">
        asdasd
      </div>
    </md-app-content>
  </md-app>
</template>

<script>

import Menu from './shared/Menu.vue';

export default {
  components: {
    pageMenu: Menu
  },
  data(){
    return{
      title: 'Cadastro',
      menuVisible: false
    }
  }
}
</script>

<style>

</style>
