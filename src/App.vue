<template>
  <div id="app">
    <div class="container">
      <div class="todolist">
        <div class="t-box accent">
          <h1 class="title">To Do List</h1>
        </div>
        <div class="i-box">
          <input
            class="input"
            v-model="task"
            type="text"
            placeholder="     Add a new task"
          />
          <button class="add-button accent" @click="addTask()">+</button>
        </div>
        <div class="l-box">
          <List :taskList="newTask" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import List from "@/components/List.vue";
export default {
  name: "App",
  data() {
    return {
      newTask: [],
      task: "",
    };
  },
  components: {
    List,
  },
  methods: {
    addTask() {
      if (!this.task) return;
      this.newTask.push({ task: this.task });
      this.task = "";
    },
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap");

* {
  font-family: "Poppins", sans-serif;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.container {
  background-color: #e3e9ff;
  width: 100%;
  height: 100vh;
  display: grid;
  place-items: center;
}

.accent {
  background-color: #af7eeb;
}

.todolist {
  width: 400px;
}

.t-box {
  box-shadow: 0px 10px 15px -3px rgba(86, 0, 107, 0.1);
  width: 100%;
  .title {
    font-size: 1.3rem;
    color: #fff;
    text-align: center;
    padding: 10px 0;
    margin-bottom: 15px;
  }
}

.i-box {
  width: 100%;
  display: flex;
  justify-content: center;
  margin-bottom: 15px;

  .input {
    width: 250px;
    border: none;
    height: 35px;
    margin-right: 10px;
    border-radius: 50px;
    outline: none;
  }

  .add-button {
    border: none;
    border-radius: 50%;
    width: 35px;
    height: 35px;
    outline: none;
    color: #fff;
    font-weight: bolder;
    font-size: 22px;
  }
}

.l-box {
  box-shadow: 0px 10px 15px -3px rgba(0, 0, 0, 0.1);
  width: 100%;
  background-color: #fff;
  min-height: 200px;
  display: flex;
  justify-content: center;
  align-items: center;

  .list {
    list-style-type: none;
  }

  .items {
    font-size: 14px;
    color: #98a0c1;
    margin-bottom: 10px;
    min-width: 250px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .delete-button {
    background-color: rgb(160, 160, 160);
    border: none;
    border-radius: 50%;
    width: 20px;
    height: 20px;
    outline: none;
    color: #fff;
    font-weight: bolder;
    font-size: 10px;
    padding-left: 1px;
  }
}
</style>
