<template>
 <ul>
  <li v-for="res in storedResource" :key="res">
  <h3>{{ res.title }}</h3>
  <p>{{ res.description }}</p>
 <a href=" res.link">click</a>
  </li>
 </ul>
</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      storedResource:[{
        id:"official",
        title:"Guide",
        description:"have to read",
        link:"www.google.com/"
      },
    {
      id:"official2",
        title:"Guide2",
        description:"have to read2",
        link:"https://www.google.com/"
    }]
    }
  },
  components: {
   
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
