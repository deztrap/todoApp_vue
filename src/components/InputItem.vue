<template>
  <div class="children">
    <div v-if="isUpdating">
      <input type="text" :placeholder="todoItemName" v-model="newTodoValue" />
      <button>Save</button>
      <button>Cancel</button>
    </div>
    <div v-else>
      <span>
        {{ todoItem }}
      </span>
      <button @click="handleDelete">Delete</button>
      <button @click="handleUpdate">Update</button>
    </div>
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
      isUpdating: false,
      // newValue: undefined,
    };
  },
  methods: {
    handleDelete() {
      this.$emit("deleteMe", this.todoItemIndex);
    },
    handleUpdate() {
      this.isUpdating = true;
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