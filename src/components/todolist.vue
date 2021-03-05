<template>
  <ul>
    <li
      v-bind:class="{ Rayure: task.checked }"
      v-for="(task, index) in tasks"
      :key="(task, index)"
    >
      <input v-on:click="rayer(index)" type="checkbox" /> {{ task.description }}
      <button v-on:click="deleteTask(index)" class="trash">🗑</button>
    </li>
  </ul>
</template>

<script>
export default {
  name: "showtask",
  props: ["tasks"],

  methods: {
    deleteTask(index) {
      this.$emit("deleteTask", index);
    },
    rayer(index) {
      this.$emit("rayer", index);
    },
  },
};
</script>

<style scoped>
.trash {
  border-radius: 100%;
  height: 50px;
  width: 50px;
}

.trash:focus {
  outline: none;
}

.Rayure {
  text-decoration: line-through;
}

li {
  display: flex;
  align-items: center;
  justify-content: space-around;
  margin-bottom: 2%;
}
</style>