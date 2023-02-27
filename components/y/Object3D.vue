<template lang="pug">
| YObject3D
div
  YEntity
  slot(:p="tp")
</template>

<script setup lang="ts">
import type { Object3D } from 'three';

const props = withDefaults(defineProps<{
  position?: Vec3,
  rotation?: Vec3,
  scale?: Vec3,
  rotationOrder?: RotationOrder,
  p?: string | undefined,
  object: Object3D
}>(), {
  position: () => ({ x: 0, y: 0, z: 0 }),
  rotation: () => ({ x: 0, y: 0, z: 0 }),
  scale: () => ({ x: 1, y: 1, z: 1 }),
  rotationOrder: "XYZ"
});
watch(() => props.position, (pos) => {
  props.object.position.set(pos.x, pos.y, pos.z)
}, { immediate: true })
watch(() => props.rotation, (rot) => {
  props.object.rotation.set(rot.x, rot.y, rot.z)
}, { immediate: true })
watch(() => props.scale, (scale) => {
  props.object.scale.set(scale.x, scale.y, scale.z)
}, { immediate: true })
watch(() => props.rotationOrder, (order) => {
  props.object.rotation.order = order;
}, { immediate: true })

const tp = genRandomString()
provide(tp, props.object)
let parent: Object3D;
if (props.p) {
  parent = inject(props.p)!
  parent.add(props.object)
}
onUnmounted(() => {
  parent?.remove(props.object)
})
</script>