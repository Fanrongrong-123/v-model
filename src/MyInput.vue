<template>
  <div>
    <input :value="value" @input="onInput" />
  </div>
</template>

<script>
export default {
  name: "MyInput",
  props: {
    value: {
      type: String,
    },
  },
  methods: {
    onInput(e) {
      const value = e.target.value;
      this.$emit("input", value); //$emit相当于eventBus将数据放到$event
    },
  },
};
</script>