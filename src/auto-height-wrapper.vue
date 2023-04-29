<template>
  <div ref='el' class='auto-height-table-wrapper'>
    <slot :size='size' />
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue';
import { useElementSize } from '@vueuse/core';
const el = ref(null);
const { width, height } = useElementSize(el);
const size = computed(() => ({
  width: width.value,
  height: height.value 
}));
</script>

<style lang="scss" scoped>
.auto-height-table-wrapper {
  height: 100%;
  overflow: hidden;
}
</style>
