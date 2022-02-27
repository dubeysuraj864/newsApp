<template>
  <div class="container">
      <h1>News App</h1>

        <div class="title">{{results.title}}</div>
        <div class="creator">{{results.creator}}</div>
        <div class="description">{{results.description}}</div>

  </div>
</template>

<script>
export default {
name: 'Card',
props:{
    results: Object
}
}
</script>

<style scoped>

</style>