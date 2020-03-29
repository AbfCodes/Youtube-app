<template>
  <div>
    <input
      type="text"
      class="form-control mt-2 mb-3"
      placeholder="Search"
      autofocus
      @input="onInput"
    />
  </div>
</template>

<script>
export default {
  name: 'Searchbar',
  data() {
    return {};
  },
  methods: {
    onInput: function(e) {
      this.$emit('valCh', e.target.value);
    }
  }
};
</script>

<style scoped>
input {
  width: 75%;
}
div {
  text-align: center;
}
</style>
