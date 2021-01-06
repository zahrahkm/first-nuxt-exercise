<template>
  <div>
    <h1>jokes</h1>
    <SearchText @search-text="searchtext"></SearchText>
    <Joke v-for="joke in jokes" :key="joke.id" :joke="joke.joke" :id="joke.id">
    </Joke>
  </div>
</template>

<script>
import Joke from "../../components/Joke";
import SerachText from "../../components/SearchText";
import axios from "axios";
export default {
  name: "Jokes",
  components: {
    Joke,
    SerachText
  },
  head() {
    return {
      title: "Jokes",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "this is a best place for description"
        }
      ]
    };
  },

  data() {
    return {
      jokes: []
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: " application/json"
      }
    };

    try {
      const res = await axios.get(`https://icanhazdadjoke.com/search`, config);
      this.jokes = res.data.results;
      console.log(res.data);
    } catch (err) {
      console.log(err);
    }
  },
  methods: {
    async searchtext(text) {
      const config = {
        headers: {
          Accept: "application/json"
        }
      };
      try {
        const res = await axios.get(
          `https://icanhazdadjoke.com/search?term=${text}`,
          config
        );
        this.jokes = res.data.results;
      } catch (err) {
        console.log(err);
      }
    }
  }
};
</script>


