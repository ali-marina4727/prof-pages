<template>
  <div>
    <input v-model="newTask" type="text" placeholder="Добавь задачу" />
    <button @click="addSomeTask" @onAddTask="task = $event">добавить</button>
  </div>
</template>

<script>
import { eventBus } from "./main.js";

export default {
  data() {
    return {
      nextId: 3,
      newTask: "",
    };
  },
  props: {
    task: {
      type: String,
      default: "d name",
    },
  },
  methods: {
    addSomeTask() {
      if (this.newTask) {
        eventBus.$emit("onAddTask", this.newTask, this.nextId);
        this.newTask = "";
        this.nextId++;
      }
      console.log(this.nextId);
    },
  },
};
</script>