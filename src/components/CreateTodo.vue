<template>
  <button v-on:click="createTodo">Add Todo</button>
</template>

<script>
import { DataStore } from "@aws-amplify/datastore";
import { Todo } from "../models";

export default {
  name: "CreateTodo",
  methods: {
    async createTodo() {
      await DataStore.save(
        new Todo({
          name: "Lorem ipsum dolor sit amet",
          description: "Lorem ipsum dolor sit amet",
          created: "1970-01-01Z",
        })
      );
    },
  },
};
</script>
