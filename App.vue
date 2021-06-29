<template>
  <main id="app">
    <section class="todolist">
      <h3>Todo List</h3>
      <add-task :task="task"></add-task>

      <cat-select :categories="categories" @on-select="onSelectCategory"></cat-select>

      <todo-list></todo-list>
    </section>
    <section class="calendar">
      <h3>Calendar</h3>
      <iframe
        style="width: 100%; height: 224px;"
        frameborder="0"
        src="http://calendar.volego.ru/informer"
      ></iframe>
    </section>

    <section class="friends">
      <h3>Contacts</h3>
      <contact-list :contacts="contacts"></contact-list>
    </section>

    <section class="posts">
      <h3>News</h3>
      <div class="post">
        <h2>Lorem ipsum</h2>
        <div class="date">
          1/01/2021
          <span class="time">12:30</span>
        </div>
        <p>
          But I must explain to you how all this mistaken idea of denouncing pleasure and praising pain was
          born and I will give you a complete account of the system, and expound the actual teachings of the
          great explorer of the truth, the master-builder of human happiness. No one rejects, dislikes, or
          avoids pleasure itself, because it is pleasure, but because those who do not know how to pursue
          pleasure rationally encounter consequences that are extremely painful.
        </p>
      </div>
    </section>
  </main>
</template>

<script>
import AddTask from "./AddTask";
import TodoList from "./TodoList";

export default {
  name: "app",
  data() {
    return {
      tasks: {
        // task: "this task 1", не нужно
      },
    };
  },
  components: {
    addTask: AddTask,
    todoList: TodoList,
  },
};
</script>

<style lang="scss">
</style>
