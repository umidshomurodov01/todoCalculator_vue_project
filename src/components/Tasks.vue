<template>
  <div class="task">
    <div v-for="task in tasks" :key="task.id">
      <Task
        :task="task"
        @delete_task="$emit('delete_task', task.id)"
        @toggle_reminder="$emit('toggle_reminder', task.id)"
      />
    </div>
  </div>
</template>

<script>
import Task from "@/components/Task.vue";
export default {
  name: "Tasks",
  props: {
    tasks: Array,
  },
  components: {
    Task,
  },
  emits: ["delete_task", "toggle_reminder"],
};
</script>

<style scoped>
.task{
    width: 100%;
}

</style>