<template>
  <div class="SearchBox">
    <form @submit.prevent="OnSubmit">
      <input type="text" v-model="text" placeholder="Search for jokes..." />
      <input type="submit" value="Search Jokes" />
    </form>
  </div>
</template>

<script>
export default {
  name: "SearchJokes",
  data() {
    return {
      text: "",
    };
  },
  methods: {
    OnSubmit() {
      this.$emit("search-text", this.text);
    },
  },
};
</script>

<style scoped>
.SearchBox {
  /* padding: 1rem; */
  margin: 1rem 1rem;
}
</style>
