<template>
  <div class=".todolist">
    <li :key="task" v-for="task in tasks">{{ task.id }}. {{task.title}}</li>
  </div>
</template>

<script>
import { eventBus } from "./main.js";

export default {
  data() {
    return {
      tasks: [
        { title: "поесть", id: 1 },
        { title: "попить", id: 2 },
      ],
    };
  },

  props: {
    task: {
      type: String,
    },
  },
  created() {
    eventBus.$on("onAddTask", (title, id) => {
      this.tasks.push({ title: title, id: id });
    });
  },
  methods: {},
};
</script>