<template>
  <div>ID is: {{ num }}</div>
</template>

<script setup lang="ts">
import { watch } from 'vue';

// 1. 可以直接从 defineProps 解构
// 2. 可以直接指定默认值
// 3. readonly
const { num = 111 } = defineProps<{
  num?: number;
}>();

// 新的，监听得到
watch(() => num, (newVal) => {
  console.log(`destructured num ${newVal}`);
});

</script>

<style lang="css">
</style>