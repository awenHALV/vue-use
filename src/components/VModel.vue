<template>
  <input type="text" :value="data" @input="update"/>
  {{data}}
</template>

<script>
import {useVModel} from '@vueuse/core';

export default {
  props: ['data'],
  setup(props, {emit}) {
    const _data = useVModel(props, 'data', emit);
    // equal to props.data
    console.log(_data.value);
    // equal to emit('update:data', 'name')
    // _data.value = 'name';

    const update = (event) => {
      _data.value = event.target.value;
    };
    return {
      _data,
      update
    }
  }
}
</script>