<template>
  <div>
    <input type="text" @input="onInput" />
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  methods: {
    onInput: function(event) {
      this.$emit("termChange", event.target.value);
    },
  },
};
</script>

<style scoped>
div {
  width: 50%;
}
input {
  width: 50%;
  height: 30px;
  border: none;
  border-radius: 15px;
  padding-left: 10px;

  box-shadow: rgb(189, 188, 188) 5px 5px 10px;
}
</style>
