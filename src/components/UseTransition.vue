<template>
  <h2>
    <p>Join over</p>
    <p>{{ Math.round(output) }}+</p>
    <p>Developers</p>
  </h2>
</template>

<script>
import { ref } from "vue";
import { useTransition, TransitionPresets } from "@vueuse/core";

export default {
  setup() {
    // 普通数值进行增加，直到5000
    const count = ref(0);
    const output = useTransition(count, {
      duration: 3000,
      transition: TransitionPresets.easeOutExpo,
    });
    count.value = 5000;

    return {
      output,
    };
  },
};
</script>