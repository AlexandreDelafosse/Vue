
<template>
  <div id="app">
    <todocard> </todocard>
  </div>
</template>


<script>
import todocard from "@/components/todocard.vue";

export default {
  name: "app",
  components: { todocard },
};
</script>

<style>
* {
  padding: 0px;
  margin: 0px;
}

body {
  background-color: rgb(216, 216, 83);
  min-height: 100vh;
}

#app {
  padding-top: 100px;
}
</style>