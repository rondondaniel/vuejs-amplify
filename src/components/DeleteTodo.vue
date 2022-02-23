<template>
  <button v-on:click="deleteTodo">Delete Todos</button>
</template>

<script>
import { DataStore } from "@aws-amplify/datastore";
import { Todo } from "../models";

export default {
  name: "DeleteTodo",
  methods: {
    async deleteTodo() {
      const modelToDelete = await DataStore.query(
        Todo,
        //Modify Todo ID with a existing entry.
        //Use Query Todos and check console output to get ID.
        "336fa235-9b21-480e-8542-a323ea243f9a"
      );
      DataStore.delete(modelToDelete);
    },
  },
};
</script>
