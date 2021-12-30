<template>
  <ul>
    <list-item
      v-for="item of todoData"
      :key="item.id"
      :item="item"
      @handleItem="handleItem"
    ></list-item>
  </ul>
</template>
<script>
import ListItem from "./ListItem";
export default {
  name: "TdList",
  components: {
    ListItem,
  },
  props: {
    todoData: Array,
  },
  methods: {
    handleItem(...args) {
      this.$emit("dispatch", ...args);
    },
  },
};
</script>
