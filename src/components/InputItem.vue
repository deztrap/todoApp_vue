<template>
  <div class="children">
    <span>
      {{ todoItem }}
    </span>
    <button @click="handleDelete">Delete</button>
    <button>Update</button>
  </div>
</template>
<script>
export default {
  props: {
    todoItem: String,
    todoItemIndex: Number,
  },
  data() {
    return {
      // newValue: undefined,
    };
  },
  methods: {
    handleDelete() {
      this.$emit("deleteMe", this.todoItemIndex);
    },
  },
};
</script>
<style scoped>
span {
  padding-top: 30px;
  padding-bottom: 30px;
  margin: 40px;
}
</style>