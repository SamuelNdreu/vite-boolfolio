<script>
  import HeaderApp from './components/HeaderApp.vue';
  import MainApp from './components/MainApp.vue';
    // import MainApp from './components/MainApp.vue';

  export default{
    name:app,
    components:{
      HeaderApp,
      MainApp,
      // MainApp,

    }
  }
</script>

<template>
  <HeaderApp/>
  <router-view></router-view>
  <!-- <MainApp/> -->
</template>