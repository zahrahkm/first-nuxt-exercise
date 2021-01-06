<template>
  <div>
    <p>{{ joke }}</p>
    <hr />
    <small>Joke's ID : {{ $route.params.id }}</small>
  </div>
</template>



<script>
import axios from "axios";
export default {
  name: "SingleJoke",
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
      joke: {}
    };
  },

  async created() {
    const config = {
      headers: {
        Accept: " application/json"
      }
    };
    try {
      const res = await axios.get(
        `https://icanhazdadjoke.com/j/${this.$route.params.id}`,
        config
      );
      this.joke = res.data.joke;
      console.log(this.joke);
    } catch (err) {
      console.log(err);
    }
  }
};
</script>