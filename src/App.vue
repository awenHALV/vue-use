<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <!-- <HelloWorld msg="Hello Vue 3 in CodeSandbox!" /> -->
  <PopOver :open="false"/>
  <TudoAndRedo />
</template>

<script>
// import HelloWorldVue from "./components/HelloWorld.vue";
import PopOver from "./components/PopOver.vue";
import TudoAndRedo from "./components/TudoAndRedo.vue";

export default {
  name: "App",
  components: {
    // HelloWorld: HelloWorldVue,
    PopOver: PopOver,
    TudoAndRedo: TudoAndRedo
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
