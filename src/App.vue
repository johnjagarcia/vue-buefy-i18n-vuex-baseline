<template>
  <div id="app">
    <navbar></navbar>
    <layout>
      <router-view />
    </layout>
  </div>
</template>

<script>
import Navbar from "./components/root/Navbar";
import Layout from "./components/root/Layout";

export default {
  name: "App",
  components: {
    Navbar,
    Layout,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
