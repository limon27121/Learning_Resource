<template>
<BaseCard>
 <div class="button-container">
 <button class="primary-button" @click="store('StoredResource')">Store Resource</button>
 <button class="secondary-button" @click="store('AddResource')">Add Resource</button>
</div>
</BaseCard>

<!-- change the components according to condition -->
<keep-alive>
 <component :is="setvalue"></component>
</keep-alive>


</template>

<script>
import BaseCard from './UI/BaseCard.vue';
import StoredResource from './StoredResource.vue';
import AddResource from './AddResource.vue';
export default {
    components:{
        BaseCard,
        StoredResource,
        AddResource
        

    },
  data(){
    return{
        setvalue:"StoredResource",
        storedResources: [
        {
          id: 'official-guide',
          title: 'Official Guide',
          description: 'The official Vue.js documentation.',
          link: 'https://vuejs.org',
        },
        {
          id: 'google',
          title: 'Google',
          description: 'Learn to google...',
          link: 'https://google.org',
        },
        {
          id: 'google',
          title: 'Google',
          description: 'Learn to google...',
          link: 'https://google.org',
        },
        {
          id: 'google',
          title: 'Google',
          description: 'Learn to google...',
          link: 'https://google.org',
        },
      ],
    }

  },
  //inject the props child to child
  provide() {
    return {
      resources: this.storedResources,
      add:this.addResource,
      remove:this.removeResource
    };
  },
  methods:{
    store(tab){

      //select the components according to condition
     this.setvalue=tab
    },
    addResource(title,description,url){
     const newResource={
      id:new Date().toISOString(),
      title:title,
      description:description,
      link:url
     }
     this.storedResources.unshift(newResource)
     this.setvalue="StoredResource"
    },
    removeResource(resId){
      const id=this.storedResources.findIndex((res)=>{
             resId!=res.id
      })
      this.storedResources.splice(id,1)
    }
  }
}
</script>

<style scoped>
  /* Apply styles to the buttons */
  .primary-button,
  .secondary-button {
    display: inline-block;
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
    border: none;
    border-radius: 4px;
    margin: 5px;
    text-align: center;
    text-decoration: none;
  }

  .primary-button {
    color: #fff;
    background-color: #3498db; /* Blue color */
  }

  .secondary-button {
    color: #fff;
    background-color: #2ecc71; /* Green color */
  }

  .button-container {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    height: 100%; /* Ensures the container takes full height */
  }
</style>