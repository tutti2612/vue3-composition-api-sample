<template>
  <section>
    <h1>Test</h1>
    <Test />
  </section>
  <hr />
  <section>
    <h1>Test2</h1>
    <Test2 />
  </section>
</template>

<script>
import Test from "./components/Test.vue";
import Test2 from "./components/Test2.vue";
export default {
  name: "App",
  components: {
    Test: Test,
    Test2: Test2,
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
  margin-top: 60px;
}
</style>
