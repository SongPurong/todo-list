<template>
  <div class="todo-lsit">
    <td-title :title="title" />
    <td-form @dispatch="dispatch" />
    <td-list :todoData="todoData" @dispatch="dispatch" />
  </div>
</template>
<script>
import TdTitle from "./TdTitle";
import TdForm from "./TdForm";
import TdList from "./TdList";
import dispatch from "@/dispatchers/todoList.js";
export default {
  name: "TodoList",
  components: {
    TdTitle,
    TdForm,
    TdList,
  },
  data() {
    return {
      title: "Todo List",
      todoData: [],
    };
  },
  methods: {
    dispatch(...args) {
      dispatch(this)(...args);
    },
  },
};
</script>
