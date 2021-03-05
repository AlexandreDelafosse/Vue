<template>
  <div id="todocard">
    <div id="hautdecarte">
      <div id="Date">
        <p>{{ date }}</p>
      </div>
      <div>
        <h1>{{ titre }}</h1>
      </div>

      <div id="Taches">
        <p>{{ tasks.length }} Taches</p>
      </div>
    </div>

    <newtodo @addTask="showtask"></newtodo>

    <todolist
      @deleteTask="noTask"
      @rayer="Coche"
      :tasks="tasks"
      id="todolist"
    >
    </todolist>
  </div>
</template>

<script>
import newtodo from "@/components/newtodo.vue";
import todolist from "@/components/todolist.vue";

export default {
  name: "todocard",
  components: { newtodo, todolist },
  data() {
    return {
      titre: "VueJs Tutorial ToDo List",
      tasks: [],
    };
  },

  computed: {
    date: function () {
      let current = new Date();
      let jour = current.toLocaleString("default", { weekday: "long" });
      let month = current.toLocaleString("default", { month: "long" });
      let date = current.getDate();
      let dateTime = jour + " " + date + " " + month;

      return dateTime;
    },
  },

  methods: {
    showtask(task) {
      this.tasks.push({ description: task, checked: false });
      console.log(task);
    },
    noTask(no) {
      this.tasks.splice(no, 1);
    },
    Coche(done) {
      if (this.tasks[done].checked === false) {
        this.tasks[done].checked = true;
      } else {
        this.tasks[done].checked = false;
      }
    },
  },
};
</script>

<style>
#todocard {
  background-color: white;
  min-height: 450px;
  width: 45%;
  border-radius: 9px;
  margin: auto;
}
#hautdecarte {
  display: flex;
  justify-content: space-around;
  padding-top: 10px;
  box-shadow: lightgrey 0px 2px 6px;
}
h1 {
  color: lawngreen;
  font-size: 20px;
}
</style>