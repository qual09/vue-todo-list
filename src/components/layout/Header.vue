<template>
  <header>
    <h1>Todo List</h1>
    <div id="nav">
      <router-link to="/">Home</router-link>|
      <router-link to="/about">About</router-link>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped>
header {
  background-color: #333;
  color: white;
  text-align: center;
  padding: 10px;
}

header a {
  color: white;
  padding-right: 5px;
  text-decoration: none;
}

header a:hover {
  text-decoration: underline;
}

header a.router-link-exact-active {
  text-decoration: underline;
}

#nav {
  margin: 5px 0;
}
</style>