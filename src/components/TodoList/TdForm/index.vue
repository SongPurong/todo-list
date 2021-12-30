<template>
  <form @submit.prevent="submitText">
    <input
      type="text"
      v-model.trim="todoText"
      placeholder="Input what you wanna to do"
    />
  </form>
</template>
<script>
export default {
  name: "TdForm",
  data() {
    return {
      todoText: "",
    };
  },
  methods: {
    submitText() {
      if (this.todoText.length === 0) return;
      this.$emit("dispatch", "ADD", {
        id: Date.now(),
        text: this.todoText,
        completed: false,
      });
      this.todoText = "";
    },
  },
};
</script>
