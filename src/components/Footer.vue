<template>
  <div class="card-footer text-muted text-center">
    Created By <a :href="url"> {{title}}</a>
  </div>
</template>

<script>
export default {
    props:['url','title']

}
</script>

<style>

</style>