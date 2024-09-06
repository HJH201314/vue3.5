<template>
  <div>ID is: {{ num }}</div>
</template>

<script setup lang="ts">
import { watch } from 'vue';

const { num = 111 } = defineProps<{
  num?: number;
}>();

// 旧的，监听不到
watch(() => num, (newVal) => {
  console.log(`destructured num ${newVal}`);
});

</script>

<style lang="css">
</style>