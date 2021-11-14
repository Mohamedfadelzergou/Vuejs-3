<template>
  <Header/>
  <div class="container mt-3">
    <div class="row">
      <Courses>
        <ol class="breadcrumb">
            <li class="breadcrumb-item"><a href="#">Home</a></li>
            <li class="breadcrumb-item active" aria-current="page">List Courses</li>
        </ol>
      </Courses>
    </div>
  </div>
  <Footer url="https://www.linkedin.com/in/mohamed-fadel-zergou-623785189/" title="Med Fadel Zergou"/>
  
</template>

<script>
import Header from './components/Header.vue';
import Courses from './components/Courses.vue';
import Footer from './components/Footer.vue';
export default {
  components: { 
    Header,
    Courses,
    Footer
    },
  name: 'App',
  data(){
    return{
      message:"Med Fadel Zergou"
    }
  },
  methods:{
    handlClick(){
      console.log(this.$refs.book.value);
      this.$refs.book.classList.add('active');
      this.$refs.book.focus();
    }
  }
}
</script>

<style>
</style>
