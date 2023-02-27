<template lang="pug">
YObject3D(:object="o1" v-slot="{p}")
  YObject3D(:object="o2" :p="p" v-if="show")
</template>

<script setup lang="ts">
import { Object3D } from 'three';

const o1 = new Object3D()
const o2 = new Object3D()
console.log(o1)
let show = ref(true)
setTimeout(() => {
  show.value = false;
}, 1000);
</script>