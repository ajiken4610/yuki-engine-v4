<template lang="pug">
| YRenderer
div
  YEntity
</template>

<script setup lang="ts">
import { WebGLRenderer } from 'three';

const props = withDefaults(defineProps<{
  width?: number,
  height?: number,
  clearColor: number
  clearAlpha: number
}>(), {
  clearColor: 0x000000,
  clearAlpha: 0
});
const emit = defineEmits<(e: "value", val: WebGLRenderer) => void>();

// prepare renderer
const renderer = new WebGLRenderer()
emit("value", renderer)

// on resize
const onResize = (w?: number, h?: number) => {
  renderer.setSize(w ?? window.innerWidth, h ?? window.innerHeight)
}
watch(() => [props.width, props.height], ([w, h]) => onResize(w, h), { immediate: true })
const resizeListener = () => onResize()
window.addEventListener("resize", resizeListener)
onUnmounted(() => {
  window.removeEventListener("resize", resizeListener)
})

// set clear color
watch(() => [props.clearColor, props.clearAlpha], ([color, alpha]) => {
  renderer.setClearColor(color!, alpha!)
}, { immediate: true })
// dispose
onUnmounted(() => {
  renderer.dispose()
})

</script>