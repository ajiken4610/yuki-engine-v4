<template lang="pug">
YObject3D(:object="o1")
  YObject3D(:object="o2")
</template>

<script setup lang="ts">
import { Object3D } from 'three';

const o1 = new Object3D()
const o2 = new Object3D()
console.log(o1)
</script>