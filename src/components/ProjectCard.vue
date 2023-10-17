<script>
export default {
  props:[
    'project'
  ]
}
</script>

<template>
  <article class="card mb-3">
  <h1 class="card-header">
    {{ project.title }}
  </h1>
  <div class="card-body">
    <img v-if="project.preview.startsWith('img/') " :src="'http://127.0.0.1:8000/storage/' + project.preview " :alt="project.title">
    <img v-else :src="project.preview " :alt="project.title">
    <p class="card-title">Author: {{ project.author }}</p>
    <p class="card-text">Date: {{ project.date }}</p>
    <p class="card-text">Type: {{ project?.type?.type ?? 'unknown' }}</p>
    <p class="card-text">Technologies: 
      <span v-if="project.technologies.length > 0" v-for="technology in project.technologies">{{ technology.technology + ' '}}</span>
      <span v-else>unknown</span>
    </p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</article>
</template>

<style lang="scss">

</style>