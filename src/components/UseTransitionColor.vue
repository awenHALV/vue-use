<template>
  <h2 :style="{ color: color }">COLOR CHANGING</h2>
</template>

<script>
import { ref, computed } from "vue";
import { useTransition, TransitionPresets } from "@vueuse/core";

export default {
  setup() {
    // 色值/位置
    const source = ref([255, 255, 255]);
    const output = useTransition(source, {
      duration: 3000,
      transition: TransitionPresets.easeOutExpo,
    });
    const color = computed(() => {
      const [r, g, b] = output.value;
      return `rgb(${r}, ${g}, ${b})`;
    });
    source.value = [0, 0, 0];

    return {
      color,
    };
  },
};
</script>