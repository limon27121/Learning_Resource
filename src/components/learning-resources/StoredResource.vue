<template>
  <ul>
   
    <learning-resource
      v-for="res in resources"
      :key="res.id"
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