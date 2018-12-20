<template>
<div>
  <md-toolbar class="md-transparent" md-elevation="0">{{menu}}Navigation</md-toolbar>

    <md-list>
      <md-list-item>
        <md-icon>move_to_inbox</md-icon>
        <router-link to="/" class="md-list-item-text">Home</router-link>
      </md-list-item>

      <md-list-item>
        <md-icon>send</md-icon>
        <router-link to="/cadastro" class="md-list-item-text">Cadastro</router-link>
      </md-list-item>
    </md-list>
  </div> 
</template>

<script>
export default {
    props: ['menu']
}
</script>
<style>

</style>
