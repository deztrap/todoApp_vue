<template>
  <div>
    <li>{{ item }}</li>
  </div>
</template>
<script>
export default {
  prop: {
    value: String,
  },
  data() {
    return {
      item: undefined,
    };
  },
};
</script>
