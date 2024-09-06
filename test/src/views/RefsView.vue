<template>
  <div ref="container" class="container">
    <div ref="item">233</div>
  </div>
</template>

<script setup lang="ts">
import { onMounted, ref, useTemplateRef } from 'vue';

const container = ref(null);
const item = ref(null);

const containerViewRef = useTemplateRef('container');
const itemViewRef = useTemplateRef('item');

onMounted(() => {
  // old
  console.log('old ref container', container.value);
  console.log('old ref item', item.value);
  // new
  console.log('new ref container', containerViewRef.value);
  console.log('new ref item', itemViewRef.value);
});
</script>

<style>
@media (min-width: 1024px) {
  .container {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
