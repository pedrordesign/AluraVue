<template>
  <div id="app" class="page-container">
    <transition name="page">
      <router-view/>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.main-header{
  top:0px;
  margin-top:0px;
}

.page-enter, .page-leave-active {
  opacity: 0;

}
.page-enter-active, .page-leave-active {
  transition: .5s

}
</style>
