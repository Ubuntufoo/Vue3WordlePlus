<script setup>
import { defineProps } from 'vue';
// eslint-disable-next-line no-unused-vars
const props = defineProps({
  letter: {
    type: String,
    default: "",
  },
  color: {
    type: String,
    default: ""
  }
})
</script>

<template>
  <div id="down-size" class="col rounded text-uppercase text-center shadow fs-1 justify-content-center align-items-center user-select-none"
    :class="{
      'bg-danger text-white'
        : color == 'gray',
      'border border-success bg-success text-white'
        : color == 'green',
      'border border warning bg-warning text-white'
        : color == 'yellow',
    }">
    <transition>
      <p v-if="letter" class="mt-1">{{ letter }}</p>
    </transition>
  </div>
</template>

<style lang="css" scoped>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

@media (max-width: 768px) {
  /* Update the CSS selector to target the desired element */
  #down-size {
    height: 50px;
    width: 50px;
  }
}

div {
  height: 80px;
  width: 80px;
}
</style>
