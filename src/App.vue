<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <!-- <h1>HelloWorld</h1> -->
  <div class="container">
    <Header title="Task Tracker"/>
    <Button text="Add Task" color="green"/>
    <Tasks @delete-task="deleteTask" :tasks="tasks" />
  </div>

</template>

<script>
import Header from './components/Header.vue'
import Button from './components/Button.vue'
import Tasks from './components/Tasks.vue'

// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    Header,
    Button,
    Tasks
    // HelloWorld
  },
  data(){
    tasks:[]
  },
  methods:{
deleteTask(id){
  if(confirm('Are you sure?')){
    this.tasks=this.tasks.filter((task)=>task.id !==id)
  console.log('task',id);
  } 
}
  },
  created(){
    this.tasks=[
      {
        id:1,
        text:'Doctors Appointment',
        day:'March 1st at 2:30pm',
        reminder:true
      },
      {
        id:2,
        text:'Market',
        day:'Jan 1st at 2:30pm',
        reminder:true
      },
      {
        id:3,
        text:'Homework',
        day:'Dec 1st at 2:30pm',
        reminder:false
      }
    ]
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>
