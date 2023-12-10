<template>
  <ul>
    <!-- data binding using loop and send data to other components -->
    <learning-resource
      v-for="res in resources"
      :key="res.id"
      :id="res.id"
      :title="res.title"
      :description="res.description"
      :link="res.link"
    ></learning-resource>
  </ul>
  
  <!-- <LearningResource :check="check"/> -->
</template>

<script>
import LearningResource from './LearningResource.vue';
export default {
inject:["resources"],
components:{
    LearningResource
},
data(){
    return{
   
    }
}
}
</script>

<style>

</style>