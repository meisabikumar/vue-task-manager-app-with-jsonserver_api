<template>
  <div :key="task.id" v-for="task in tasks">
    <Task
      @toogle-reminder="$emit('toogle-reminder', task.id)"
      @delete-task="$emit('delete-task', task.id)"
      :task="task"
    />
  </div>
</template>

<script>
import Task from "./Task.vue";

export default {
  name: "Tasks",
  props: {
    tasks: Array,
  },
  components: {
    Task,
  },
  emits: ["delete-task", "toogle-reminder"],
};
</script>

<style  scoped>
</style>