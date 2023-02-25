<template lang="pug">
YObject3D(:object="object")
</template>
<script setup lang="ts">
import { Object3D } from 'three';

const object = new Object3D();
</script>