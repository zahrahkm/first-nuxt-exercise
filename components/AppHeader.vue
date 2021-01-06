<template>
  <header class="header">
    <h1 class="title">Dad Jokes</h1>
    <ul>
      <li>
        <nuxt-link to="/">Home</nuxt-link>
        <nuxt-link to="/Jokes">Jokes</nuxt-link>
        <nuxt-link to="/About">About</nuxt-link>
      </li>
    </ul>
  </header>
</template>



<script>
export default {
  name: "AppHeader"
};
</script>



<style>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.3rem;
  padding-bottom: 0.3rem;
  border-bottom: 1px dotted #ccc;
  background: #e6e6e6;
}
.header li {
  list-style: none;
}
.header .title {
  font-size: 3rem;
  color: #526488;
}
.header ul {
  display: flex;
}
.header a {
  display: inline-block;
  background: #333;
  color: #fff;
  padding: 0.2rem 1rem;
  margin-right: 0.5rem;
  text-decoration: none;
}
</style>