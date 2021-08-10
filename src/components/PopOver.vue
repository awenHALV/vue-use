<template>
  <button @click="open = true"> 123123123{{open}}</button>
  <div class="popup" v-if=open>
    <div class="popup-content" ref="popup">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Corporis aliquid autem reiciendis eius accusamus sequi, ipsam corrupti vel laboriosam necessitatibus sit natus vero sint ullam! Omnis commodi eos accusantium illum?
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'
import { onClickOutside } from '@vueuse/core'
export default {
  setup() {
  const open = ref(false) // state of our popup
  const popup = ref() // template ref
  // whenever our popup exists, and we click anything BUT it
  onClickOutside(popup, () => {
    open.value  = false
  })
  return {
    open,
    popup
  }
}


}

// const handelClick = () => {
//   this.open = !this.open;
// }


</script>

<style scoped>
  button {
    border: none;
    outline: none;
    margin-right: 10px;
    background-color: #2ecc71;
    color: white;
    padding: 5px 10px;;
  }
  .popup {
    position: fixed;
    top:;
    left:;
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    background: rgba(, , , 0.1);
  }
  .popup-content {
    min-width: 300px;
    padding: 20px;
    width: 30%;
    background: #fff;
  }
</style>