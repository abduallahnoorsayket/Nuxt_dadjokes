<template>
  <div>
    <h1>this is the about page of jokes</h1>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      jokes: [],
    };
  },
  created() {
    const config = {
      headers: {
        Accept: "application/json",
      },
    };
    try {
      const res = axios.get("https://icanhazdadjoke.com/search", config);
      console.log("24", res.data.results);
      this.jokes = res.data.results;
    } catch (error) {
      console.log(error);
    }
  },
  head() {
    return {
      title: "Dad Jokes ",
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: "description",
          name: "description",
          content: "My ABout description of dad jokes",
        },
      ],
    };
  },
};
</script>

<style></style>
