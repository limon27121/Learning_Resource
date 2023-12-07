<template>
  
  
   <Header/>
   <TheResource/>
  <!-- <stored-resources :resources="storedResources"/> -->


</template>

<script>
import StoredResources from './components/learning-resources/StoredResource.vue';
import Header from './components/learning-resources/Header.vue';
import TheResource from './components/learning-resources/TheResource.vue';
import AddResource from './components/learning-resources/AddResource';




export default {
  components: {
  
    StoredResources,
    Header,
    TheResource,
    AddResource
  },
  data() {
    return {
      // storedResources: [
      //   {
      //     id: 'official-guide',
      //     title: 'Official Guide',
      //     description: 'The official Vue.js documentation.',
      //     link: 'https://vuejs.org',
      //   },
      //   {
      //     id: 'google',
      //     title: 'Google',
      //     description: 'Learn to google...',
      //     link: 'https://google.org',
      //   },
      // ],
    };
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>