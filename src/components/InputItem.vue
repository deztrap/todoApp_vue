<template>
  <div>
    <p>{{ todoItem }}</p>
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
    // handleChange(event) {
    //   //this.todoitem = event.target.value;
    // },
  },
};
</script>
