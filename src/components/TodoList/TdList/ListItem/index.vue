<template>
  <li>
    <input
      type="checkbox"
      :checked="item.completed ? 'checked' : ''"
      @click="handleItem('COMPLETED', item.id)"
    />
    <span class="text" :class="{ completed: item.completed }">{{
      item.text
    }}</span>
    <button @click="handleItem('REMOVE', item.id)">删除</button>
  </li>
</template>
<script>
export default {
  name: "ListItem",
  props: {
    item: Object,
  },
  methods: {
    handleItem(...args) {
      this.$emit("handleItem", ...args);
    },
  },
};
</script>
<style scoped>
.completed {
  text-decoration: line-through;
}
li {
  display: flex;
  align-items: center;
  margin-bottom: 1em;
}
.text {
  flex: 1;
  padding-left: 1em;
  text-align: left;
}
</style>
