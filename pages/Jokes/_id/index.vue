<template>
  <div>
    <nuxt-link to="/jokes">Back to Jokes </nuxt-link>
    <h2>{{ joke }}</h2>
    <hr />
    <small> Joke ID : {{ $route.params.id }}</small>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      joke: {},
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json",
      },
    };
    try {
      const res = await axios.get(
        `https://icanhazdadjoke.com/j/${this.$route.params.id}`,
        config
      );

      this.joke = res.data.joke;
      // console.log("25", this.joke);
    } catch (error) {
      console.log(error);
    }
  },
  head() {
    return {
      title: this.joke,
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
