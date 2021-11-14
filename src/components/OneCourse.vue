<template>
  <div class="card my-3">
        <img class="card-img-top" :src="image" :alt="title">
        <div class="card-body">
            <h4 class="card-title">{{title}}</h4>
            <button class="btn btn-sm btn-danger" @click="deleteOne(id)">delete</button>
        </div>
    </div>
</template>

<script>
export default {
    props:['image','title','id'],
    methods:{
        deleteOne(id){
            this.$emit('delete',id);
        }
    }
}
</script>

<style>

</style>