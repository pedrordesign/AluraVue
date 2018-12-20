<template>
    <img :src="url" :alt="title" style="max-width:100%; max-height:100%" />
</template>
<script>
export default {
    props:['url', 'title']
}
</script>
<style>
</style>