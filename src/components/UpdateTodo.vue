<template>
  <button v-on:click="updateTodo">Update Todo</button>
</template>

<script>
import { DataStore } from "@aws-amplify/datastore";
import { Todo } from "../models";

let output;

async function start() {
  const original = await DataStore.query(
    Todo,
    "62abff40-1d06-4620-bf21-f6afb3f9e8f6"
  );
  output = original;
}

start();

export default {
  name: "UpdateTodo",
  methods: {
    async updateTodo() {
      /* Models in DataStore are immutable. To update a record you must use the copyOf function to apply updates to the item’s fields rather than mutating the instance directly */
      DataStore.save(
        Todo.copyOf(output, (item) => {
          // Update the values on {item} variable to update DataStore entry
          item.name = "name myName";
        })
      );
    },
  },
};
</script>
