<template>
  <div>
    <input type="text" :placeholder="todoItemName" v-model="newTodoValue" />
    <button @click="handleSave">Save</button>
    <button @click="handleCancel">Cancel</button>
  </div>
</template>
<script>
export default {
  name: "UpdateItem",
  prop: {
    value: String,
  },
  data() {
    return {
      newTodoValue: undefined,
    };
  },
  methods: {
    handleCancel() {
      this.$emit("cancel");
    },
    handleSave() {
      this.$emit("save", this.newTodoValue);
    },
  },
};
</script>
