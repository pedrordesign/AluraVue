<template>
  <div class="md-card">
    <div class="md-card-header" @dblclick="visible = !visible">
      <div class="md-title">{{titulo}}</div>
    </div>
    <transition name="panel-fade">
      <div class="md-card-content" v-show="visible">
        <slot></slot>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  props: ['titulo'],
  
  data(){
    return{
      visible: true
    }
  }
}
</script>

<style scoped>
  .panel-fade-enter, .panel-fade-leave-active {
    opacity: 0;

  }
  .panel-fade-enter-active, .panel-fade-leave-active {
    transition: .5s

  }
</style>
