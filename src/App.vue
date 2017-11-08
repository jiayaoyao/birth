<template>
  <div id="app">
    <main>
      <controls/>
      <demo/>
    </main>
  </div>
</template>

<script>
import controls from "./components/Controls";
import demo from "./components/Demo";
export default {
  name: "app",
  components: {
    controls,
    demo
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
main {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  min-height: 800px;
  border: solid 40px #e9ecf1;
  background-color: #fcfcfc;
}
</style>