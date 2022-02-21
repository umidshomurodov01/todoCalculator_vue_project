<template>
  <div class="container">
    <Header
    :showAddTask="showAddTask" 
    @toggle_add_task="toggleAddTask()" 
     title="Calculator"
     />
    <div v-show="showAddTask">
     <AddTask @add_task="AddTask"/>
    </div>
   <Tasks :tasks="tasks" @delete_task="deleteTask" @toggle_reminder="toggleReminder" />

    <Footer/>
  </div>
</template>

<script>
import AddTask from "@/components/AddTask.vue";
import Header from "@/components/Header.vue";
import Tasks from "@/components/Tasks.vue";
import Footer from "@/components/Footer.vue";
export default {
  components: {
    Header,
    Tasks,
     AddTask,
     Footer,
  },
  data() {
    return {
      tasks: [],
      showAddTask:false,
    };
  },
  methods: {
    toggleAddTask(){
      this.showAddTask = !this.showAddTask
      console.log(this.showAddTask)
    },
    AddTask(task){
      this.tasks = [...this.tasks, task]
    },
    deleteTask(id) {
      if (confirm("Are You Sure?")) {
        this.tasks = this.tasks.filter((task) => task.id !== id);
      }
    },
     toggleReminder(id){
   this.tasks = this.tasks.map((task) => task.id === id ? {...task, reminder: !task.reminder} : task)
  },
  },
 


  created() {
    this.tasks = [
     
    ];
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
body {
  font-family:cursive;
  background: whitesmoke;
}
.container {
  max-width: 600px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border-radius: 5px;
  padding: 30px;
  box-shadow: 0 0 10px 8px #999;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  font-weight: bold;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
  transition: .5s;
}
.btn:hover{
   background: #222;

}

</style>