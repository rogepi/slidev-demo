<script setup lang="ts">

const props = defineProps({
  text: {
    default: '',
  },
})

</script>

<template>
  <div v-click class="mt-10 text-3xl slidev-vclick-target slidev-vclick-hidden">
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{{ props.text }}
  </div>
</template>

<style >
.slidev-vclick-target {
  transition: opacity 1000ms ease;
}

.slidev-vclick-hidden {
  opacity: 0;
  pointer-events: none;
}
</style>
