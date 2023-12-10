<template>
  <div class="card">
    <form @submit.prevent="submitResource">
      <div class="form-control">
        <label for="title">Title</label>
        <input id="title" name="title" type="text" v-model="title" />
      </div>
      <div class="form-control">
        <label for="description">Description</label>
        <textarea id="description" name="description" rows="3" v-model="description"></textarea>
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input id="link" name="link" type="url" v-model="link" />
      </div>
      <div>
        <base-button @click="submitResource">Add Resource</base-button>
      </div>
    </form>
    
  </div>
</template>
<script>
export default {
  data() {
    return {
    
        title: '',
        description: '',
        link: ''
    };
  },
  inject:["add"],
  methods: {
    submitResource() {
      const newTitle=this.title;
      const newDescription=this.description
      const newLink=this.link
      if (newTitle.trim() === "" || newDescription.trim() === "" || newLink.trim() === "") {
        alert("Invalid Input");
      }
      else{
      this.add(newTitle,newDescription,newLink)
      }
    }
  }
};
</script>

<style scoped>
  form {
    max-width: 400px;
    margin: 0 auto;
  }

  .form-control {
    margin-bottom: 20px;
  }

  label {
    display: block;
    margin-bottom: 5px;
  }

  input[type="text"],
  input[type="url"],
  textarea {
    width: 100%;
    padding: 8px;
    margin-top: 5px;
    box-sizing: border-box;
    border: 1px solid #ccc;
    border-radius: 4px;
    font-size: 16px;
  }

  textarea {
    resize: vertical;
  }

  base-button {
    background-color: #3498db;
    color: #fff;
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
    border: none;
    border-radius: 4px;
  }

  base-button:hover {
    background-color: #2980b9;
  }
  .card {
    max-width: 400px;
    margin: 0 auto;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 14px 18px rgba(0, 0, 0, 0.1);
    background-color: #fff;
  }
</style>
