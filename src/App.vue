
<template>
  <header>
    <div class="container">
      <Header title="Task Tracker" 
      @toggle-add-task="showAddTask = !showAddTask"
      :showAddTask="showAddTask"
      />
      <div v-show="showAddTask">
        <AddTask @add-task="addTask"/>
      </div>
      <Tasks 
        :tasks="tasks" 
        @delete-task="deleteTask" 
        @toggle-reminder="toggleReminder"
      />
      
    </div>
  </header>

  <main>
  </main>
</template>

<script>
import Header from './components/Header.vue';
import Tasks from './components/Tasks.vue';
import AddTask from './components/AddTask.vue';

export default {
  name: 'App',
  components: {
    Header,
    AddTask,
    Tasks,
  },
  data() {
    return {
      tasks: [],
      showAddTask: false,
    };
  },
  methods: {
    addTask(task) {
      const id = Math.floor(Math.random() * 100000) + 1;
      const newTask = { id, ...task };
      this.tasks.push(newTask);
    },
    deleteTask(id) {
      if (confirm('Are you sure?')) {
        this.tasks = this.tasks.filter((task) => task.id !== id);
      }
    },
    toggleReminder(id) {
      this.tasks = this.tasks.map((task) => 
        task.id === id ? { ...task, reminder: !task.reminder } : task
      );
    },
  },
  created() {
    this.tasks = [
        {
          id: 1,
          text: 'Doctors Appointment',
          day: 'Feb 5th at 2:30pm',
          reminder: true,
        },
        {
          id: 2,
          text: 'Meeting at School',
          day: 'Feb 6th at 1:30pm',
          reminder: true,
        },
        {
          id: 3,
          text: 'Food Shopping',
          day: 'Feb 5th at 2:30pm',
          reminder: false,
        },
        {
          id: 4,
          text: 'Gym',
          day: 'Feb 5th at 5:30pm',
          reminder: false,
        }
      ];
  },
};

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