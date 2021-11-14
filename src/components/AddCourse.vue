<template>
    <form @submit.prevent="newCourse">
    <div class="form-group">
        <label for="title">Title</label>
        <input v-model="title" id="title" type="text" class="form-control">
    </div>
    <div class="form-group">
        <label for="image">Image</label>
        <input v-model="image" id="image" type="text" class="form-control">
    </div>
    <div class="form-group">
         <label for="category" >Category</label>
          <select v-model="category" id="category" class="form-control">
              <option :value="category.id" v-for="category in categories">{{category.name}}</option>
          </select>
    </div>
    <div class="form-check">
        <label class="form-check-label mx-3 my-2">
        <input type="radio" class="form-check-input" v-model="payment" value="free">
        Free
      </label>
      <label class="form-check-label mx-3 my-2">
        <input type="radio" class="form-check-input" v-model="payment" value="Paying" checked>
        Paying
      </label>
    </div>
    <div class="form-check">
      <label class="form-check-label">
        <input type="checkbox" class="form-check-input" v-model="published">
        Published
      </label>
    </div>
    <div class="form-check"  v-for="tag in tags">
      <label class="form-check-label">
        <input type="checkbox" class="form-check-input" v-model="mytags" :value="tag">
        {{tag}}
      </label>
    </div>
    <button type="submit" class="btn btn-warning btn-block form-control mt-2">Add Course</button>
    </form>
    <div class="well">
        <p> title : {{title}} </p>
        <p> image : {{image}} </p>
        <p> category : {{category}} </p>
        <p> payment: {{payment}} </p>
        <p> published : {{published}} </p>
        <p> tags : {{mytags}} </p>
    </div>
</template>

<script>
export default {
    data(){
        return{
            title:"",
            image:"",
            categories:[
                {
                    id:1,
                    name:"FrontEnd"
                },
                {
                    id:2,
                    name:"BackEnd"
                },
                {
                    id:3,
                    name:"FullStack"
                },
                {
                    id:4,
                    name:"Mobile"
                }
            ],
            category:"",
            payment:"Paying",
            published:false,
            tags:[
                "framework",
                "backend",
                "frontend",
                "laravel"
            ],
            mytags:[]
        }
    },
methods:{
    newCourse(){
        let title=this.title;
        let image = this.image;
        if(title == "" || image == ""){
            return;
        }
        const course={
            title,
            image
        }
        this.$emit('add',course)
        this.title="";
        this.image="";
    }
}
}
</script>

<style>

</style>