<template>
  <div class="children">
    <div v-if="isUpdating">
      <update-item @cancel="handleCancel" />
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
import UpdateItem from "./UpdateItem.vue";
export default {
  name: "InputItem",
  components: {
    UpdateItem,
  },
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
    handleCancel() {
      this.isUpdating = false;
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