<template>
  <div id="new">
    <div id="add">
      <input v-model="task" placeholder="Ajouter une tâche" id="message" />

      <button id="add-task" type="text" v-on:click="addTask">+</button>
    </div>
  </div>
</template>

<style>
#add-task {
  height: 30px;
  width: 30px;
  border-radius: 100%;
  background: green;
  border: none;
  margin: 5px;
}

#add-task:focus {
  outline: none;
}
#message {
  border-bottom-color: lightblue;
  background-color: white;
  border-left: none;
  border-top: none;
  border-right: none;
}

#add {
  padding-top: 20px;
  width: 27.5%;
  margin: auto;
}
</style>

<script>
export default {
  name: "newtodo",
  data() {
    return {
      task: "",
    };
  },

  methods: {
    addTask() {
      this.$emit("addTask", this.task);
      document.getElementById("message").value = "";
    },
  },
};
</script>
