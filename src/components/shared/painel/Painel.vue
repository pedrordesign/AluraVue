<template>
  <div class="md-content demo md-theme-demo-light">
    <div class="demo-content">
      <div class="md-layout">
        <div v-for="img of filteredImgs" class="md-layout-item md-medium-size-30 md-small-size-50 md-xsmall-size-90">
          <div class="md-card md-theme-demo-light">
            <div class="md-card-header">
              <div class="md-title">{{img.titulo}}</div>
            </div>
            <div class="md-card-content">
              <img :src="img.url" :alt="img.titulo" style="max-width:100%; max-height:100%" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['imgs'],
  
  computed:{
    filteredImgs
  }
}
</script>

<style scoped>
</style>
