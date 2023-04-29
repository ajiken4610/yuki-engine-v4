<template lang="pug">
YScene(@value="scene=$event" v-slot="{p}")
  YLight(:object="light" :p="p")
</template>

<script setup lang="ts">
import { Light, type Scene } from 'three';
const light = new Light(0xff0000)
let scene: Scene
onMounted(() => {
  console.log(scene)
})
</script>