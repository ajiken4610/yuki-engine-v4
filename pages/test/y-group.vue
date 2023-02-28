<template lang="pug">
YScene(@value="scene=$event" v-slot="{p:p0}")
  YGroup(:p="p0" v-slot="{p:p1}")
    YGroup(:p="p1")
</template>

<script setup lang="ts">
import type { Scene } from 'three';

let scene: Scene
onMounted(() => {
  console.log(scene)
})
</script>