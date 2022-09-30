<template>
  <div>
    <search-jokes v-on:search-text="searchText" />
    <joke
      v-for="joke in jokes"
      :key="joke.id"
      :id="joke.id"
      :joke="joke.joke"
    />
  </div>
</template>

<script>
import axios from "axios";
import Joke from "../../components/Joke.vue";
import SearchJokes from "../../components/SearchJokes.vue";

export default {
  components: { Joke, SearchJokes },
  data() {
    return {
      jokes: [],
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json",
      },
    };
    try {
      const res = await axios.get("https://icanhazdadjoke.com/search", config);
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
  methods: {
    async searchText(text) {
      const config = {
        headers: {
          Accept: "application/json",
        },
      };
      try {
        const res = await axios.get(
          `https://icanhazdadjoke.com/search?term=${text}`,
          config
        );
        this.jokes = res.data.results;
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>

<style></style>
