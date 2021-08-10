<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <!-- <HelloWorld msg="Hello Vue 3 in CodeSandbox!" /> -->
  <div>
    <UseInterSectionObserver />
    <UseTransition />
    <UseTransitionColor />
    <PopOver :open="false" />
    <TudoAndRedo />
    <VModel :data="data" @update:data="data = $event" />
  </div>
</template>

<script>
import { ref } from "vue";
// import HelloWorldVue from "./components/HelloWorld.vue";
import PopOver from "./components/PopOver.vue";
import TudoAndRedo from "./components/TudoAndRedo.vue";
import VModel from "./components/VModel.vue";
import UseInterSectionObserver from "./components/UseInterSectionObserver.vue";
import UseTransitionColor from "./components/UseTransitionColor.vue";
import UseTransition from "./components/UseTransition.vue";
export default {
  name: "App",
  components: {
    // HelloWorld: HelloWorldVue,
    PopOver: PopOver,
    TudoAndRedo: TudoAndRedo,
    VModel: VModel,
    UseInterSectionObserver: UseInterSectionObserver,
    UseTransition: UseTransition,
    UseTransitionColor: UseTransitionColor,
  },
  setup() {
    const data = ref("hello");
    return {
      data,
    };
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
