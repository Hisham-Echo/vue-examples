<template>
  <div class="list">
    <form action="">
      <input typr="text" placeholder="Type Your Task" v-model="taskText" />
      <button @click.prevent="addTask" :disabled="!taskText">Add Task</button>
      <button
        class="delete-all"
        :disabled="this.tasks.length <= 1 ? true : false"
        @click.prevent="deleteAll"
      >
        Delete All
      </button>
    </form>
    <div class="tasks-list" v-for="(task, index) in tasks" :key="index">
      <div
        class="task-box"
        @click="changeStatus(task)"
        :style="{ 'text-decoration': task.done ? 'line-through' : '' }"
      >
        {{ task.words }}
        <input
          class="check"
          type="checkbox"
          :checked="task.done"
          :style="{ 'accent-color': task.done ? '#3f7' : '#f00' }"
        />
      </div>
      <span class="delete" @click="deleteTask(index)">Delete</span>
    </div>
  </div>
</template>

<style lang="scss" scoped>
* {
  box-sizing: border-box;
}

body {
  font-size: 18px;
  font-family: "Open Sans", sans-serif;
}

.list {
  text-align: center;

  form {
    margin: 20px auto 10px;
    width: 500px;
    overflow: hidden;

    input {
      background-color: #f7f7f7;
      border: 1px solid #eee;
      margin-bottom: 15px;
      width: calc(100% - 210px);
      height: 46px;
      padding: 10px;
      float: left;

      &:focus {
        outline: none;
      }
    }

    button {
      width: 90px;
      height: 46px;
      background-color: #2196f3;
      color: #fff;
      border-color: transparent;
      cursor: pointer;
      float: left;
      margin-left: 5px;

      &:disabled {
        opacity: 0.4;
        cursor: not-allowed;
      }

      &:focus {
        outline: none;
      }

      &.delete-all {
        width: 110px;
        background-color: #f44336;
      }
    }
  }

  .tasks-list {
    width: 500px;
    margin: 0 auto;

    .task-box {
      background-color: rgba(139, 195, 74, 0.25);
      padding: 15px;
      text-align: left;
      margin-bottom: 15px;
      margin-right: 5px;
      width: calc(100% - 86px);
      cursor: pointer;
      float: left;
      .check {
        float: right;
      }
    }

    .delete {
      float: right;
      width: 80px;
      background-color: #f44336;
      color: #fff;
      border-color: transparent;
      padding: 1px 10px;
      height: 48px;
      line-height: 45px;
    }
  }
}
</style>

<script>
export default {
  name: "ToDoListCom",
  data() {
    return {
      tasks: [],
      taskText: "",
    };
  },
  methods: {
    updateDatabase: function () {
      localStorage.setItem("Tasks", JSON.stringify(this.tasks));
    },
    addTask: function () {
      this.tasks.push({ words: this.taskText, done: false });
      this.taskText = "";
      this.updateDatabase();
    },
    deleteTask: function (index) {
      this.tasks.splice(index, 1);
      this.updateDatabase();
    },
    deleteAll: function () {
      this.tasks = [];
      this.updateDatabase();
    },
    loadTasks: function () {
      this.tasks = JSON.parse(localStorage.getItem("Tasks"));
    },
    changeStatus: function (task) {
      task.done = !task.done;
      this.updateDatabase();
    },
  },
  mounted() {
    this.loadTasks();
  },
};
</script>
