<template>
    <div class="row" v-if="showfr">
        <div class="col-md-6  mx-auto">
            <AddCourse @add="addcourse($event)"/>
        </div>
    </div>
    <div class="row mt-3">
        <div class="col-md-6 ">
            
            <nav aria-label="breadcrumb">
            <slot></slot>
            </nav>
            <h1> List Of Courses</h1>
        </div>
        <div class="col-md-6 text-right">
            <button class="btn btn-sm text-right" :class="{'btn-success':!showfr,'btn-dark':showfr}" @click="showForm">
                {{ showfr ? 'Close':'New' }}
            </button>
        </div>
    </div>
  <div class="row">
      <div class="col-md-4" v-for="course in courses" :key="course.id">
          <OneCourse :image="course.image" :title="course.title" :id="course.id" @delete="deleteOneCourse($event)"/>
      </div>
  </div>
</template>

<script>
import AddCourse from './AddCourse.vue'
import OneCourse from './OneCourse.vue'
export default {
  components: { OneCourse, AddCourse },
    data(){
        return{
            showfr:false,
            courses:[
                {
                   id:1,
                   title:"learn react js",
                   image:"https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/C2oT8I1eTXGg69ytJ69f"
                },
                {
                    id:2,
                    title:"learn angular js",
                    image:"https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/nrOHB2iQTIiGe7hHX9O0"
                },
                {
                   id:3,
                   title:"learn vue js",
                   image:"https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/k7Fltx5ITbu9LI6VtgTS"
                },
                {
                    id:4,
                    title:"learn git",
                    image:"https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/evNSVH9RSjW0um2vBYW9"
                },
                {
                   id:5,
                   title:"learn javascripte",
                   image:"https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/H9QyEOsSLG05qNb2kC0V"
                },
                {
                    id:6,
                    title:"learn spring boot",
                    image:"https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/5miGPBu8RbCSc4hCzN39"
                },
            ]

        }
    },
    methods:{
        deleteOneCourse(id){
            this.courses = this.courses.filter(course => course.id != id)
        },
        addcourse(course){
           // this.courses.unshift(course);
           //this.courses.push(course);
           this.courses=[...this.courses,course];
        },
        showForm(){
            this.showfr=!this.showfr;
        }
    }
}
</script>

<style scoped>
h1{
    color:red;
}
</style>