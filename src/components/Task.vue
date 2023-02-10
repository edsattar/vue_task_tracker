<template>
  <div :class="[task.reminder ? 'reminder' : '', 'task']"
  @dblclick="$emit('toggle-reminder', task.id)">
    <h3>
      {{ task.text }}
      <font-awesome-icon class="delete-task" icon="fas fa-rectangle-xmark" size="xl" 
      @click="$emit('delete-task', task.id)" />
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>

<script>
export default {
    name: 'Task',
    props: {
      task: Object,
    },
  };
</script>

<style scoped>

  .delete-task {
    color: #c73131;
  }

  .task {
    background: hsl(0, 0%, 22%);
    margin: 5px;
    padding: 10px 20px;
    cursor: pointer;
  }

  .task:hover {
    background: #313131;
  }

  .task.reminder {
    border-left: 5px solid green;
  }

  .task h3 {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>