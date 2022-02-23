<template>
  <button v-on:click="queryTodos">Query Todos</button>
</template>

<script>
import { DataStore } from "@aws-amplify/datastore";
import { Todo } from "../models";

export default {
  name: "QueryTodos",
  methods: {
    async queryTodos() {
      const models = await DataStore.query(Todo);
      console.log(models);
    },
  },
};
</script>
