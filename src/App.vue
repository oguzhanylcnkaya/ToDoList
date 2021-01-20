<template>
  <div>
    <input type="text" v-model="job"/>
    <input type="button" @click="addJob" value="Add" />

    <h1>TO DO LİST</h1>
    <hr />
    <ul v-for="(item, index) in todolist" :key="item">
      <li>{{item}}</li><button @click="deleteJob(index)">X</button>
    </ul>
  </div>
</template>

<script>
export default {
  data(){
    return{
      job : "",
      todolist : []
    }
  },
  methods : {
    addJob(){
      this.todolist.push(this.job);
      this.job = "";
    },
    deleteJob(index){
      this.todolist.splice(index, 1);
    }
  }
}
</script>

<style>

</style>