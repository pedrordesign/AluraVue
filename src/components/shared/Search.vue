<template>
  <div class="md-layout md-gutter">
    <div class="md-layout-item">
      <md-field>
        <label>{{searchLabelTitle}}</label>
        <md-input v-model="search"></md-input>
      </md-field>
    </div>
  </div>
</template>
<script>
export default {
  props:['searchLabelTitle'],
  data(){
    return{
      search: ''
    }
  }
}
</script>

<style>
</style>