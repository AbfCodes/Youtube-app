<template>
  <div
    class="fl navbar navbar-expand-lg navbar navbar-dark bg-dark"
    style="background-color: #212121;"
  >
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarTogglerDemo03"
      aria-controls="navbarTogglerDemo03"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="input-group container col-md-6">
      <input
        type="text"
        class="form-control mt-1 mb-1"
        placeholder="Search"
        autofocus
        v-model="querytext"
      />
      <div class="input-group-append">
        <button
          class="input-group-text btn"
          style="padding:10px 28px;"
          @click="onInput"
        >
          <svg
            class="bi bi-search"
            width="1em"
            height="1em"
            viewBox="0 0 16 16"
            fill="currentColor"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              d="M10.442 10.442a1 1 0 011.415 0l3.85 3.85a1 1 0 01-1.414 1.415l-3.85-3.85a1 1 0 010-1.415z"
              clip-rule="evenodd"
            />
            <path
              fill-rule="evenodd"
              d="M6.5 12a5.5 5.5 0 100-11 5.5 5.5 0 000 11zM13 6.5a6.5 6.5 0 11-13 0 6.5 6.5 0 0113 0z"
              clip-rule="evenodd"
            />
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Searchbar',
  data() {
    return {
      querytext: ''
    };
  },
  methods: {
    onInput: function() {
      this.$emit('valCh', this.querytext);
    }
    // onInput: function() {
    //   this.$emit('valCh', e.target.value);
    // }
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
.fl {
  display: flex;
}
</style>
