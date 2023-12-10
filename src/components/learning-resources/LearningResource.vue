<template>
  <BaseCard>
  <li>
    <header>
        <h3>{{ title }}</h3>
        <button class="b1" @click="remove(id)">Delete</button>
      </header>
   
    <p>{{ description }}</p>
    <nav>
      <a :href="link" target="_blank">View Resource</a>
    </nav>
  </li>
  <!-- <h1>{{ check }}</h1> -->

</BaseCard>

</template>

<script>
import BaseCard from './UI/BaseCard.vue'
export default {
  //catch the value from parent using props
  props: ['id','title', 'description', 'link',"check"],
  inject:['remove'],
  components:{
    BaseCard
  }
}
</script>

<style scoped>
li {
  margin: 10px;
  max-width: 40rem;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

h3 {
  font-size: 1.25rem;
  margin: 0.5rem 0;
}

p {
  margin: 0.5rem 0;
}

a {
  text-decoration: none;
  color: #ce5c00;
}
.b1{
  background-color: blue; /* Change this color code */
    color: white;
    padding: 10px 15px;
    border: none;
    cursor: pointer;
  
}

a:hover,
a:active {
  color: #c89300;
}
</style>