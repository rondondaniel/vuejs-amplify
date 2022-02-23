<template>
  <div class="crud">
    <h1>This is an about page</h1>
    <create-todo />
    <query-todos />
    <update-todo />
    <delete-todo />
  </div>
</template>

<script>
import CreateTodo from "@/components/CreateTodo.vue";
import QueryTodos from "@/components/QueryTodos.vue";
import DeleteTodo from "@/components/DeleteTodo.vue";
import UpdateTodo from "@/components/UpdateTodo.vue";

export default {
  components: { CreateTodo, QueryTodos, DeleteTodo, UpdateTodo },
};
</script>
