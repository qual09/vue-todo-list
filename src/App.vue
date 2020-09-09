<template>
  <div id="app">
    <Header />
    <router-view />
    <Footer />
  </div>
</template>

<script>
import Header from "./components/layout/Header";
import Footer from "./components/layout/Footer";

export default {
  name: "app",
  components: {
    Header,
    Footer,
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

.container {
  background: #eee;
  border: 1px solid lightgray;
  border-radius: 10px;
  min-width: 380px;
  max-width: 900px;
  margin: 10px auto;
  padding: 20px;
  width: 80%;
}

.btn {
  display: inline-block;
  border: none;
  background-color: #555;
  color: white;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background-color: #666;
}
</style>
