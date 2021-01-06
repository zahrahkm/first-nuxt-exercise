<template>
  <div>
    <h1>About dad's jokes</h1>
    <p>This page is created to display corny dad</p>
  </div>
</template>
<script>
export default {
  name: "about",
  head() {
    return {
      title: "About the app",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "this is a best place for description"
        }
      ]
    };
  }
};
</script>

<style scoped>
</style>