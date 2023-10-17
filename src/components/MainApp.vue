<script>
  import axios from 'axios';
  import ProjectCard from './ProjectCard.vue'

  export default{
    name: 'mainApp',
    components:{
      ProjectCard,
    },

    data() {
      return {
        projectsUrl: 'http://127.0.0.1:8000/api/projects',
        projects: '',
      }
    },
    methods:{
      gatProjectsApi(){
        axios.get(this.projectsUrl, {
          params: {
          }
        })
          .then((response)=>{
            console.log(response.data.results.data)
            this.projects = response.data.results.data
          })
          .catch(function (error) {
          console.log(error);
          })
      }
    },
    created(){
      this.gatProjectsApi()
    }
  }
</script>

<template>

  <div v-for="project in projects">
    <ProjectCard 
      :project="project"
    />

  </div>

</template>