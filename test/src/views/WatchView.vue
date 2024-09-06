<template>
  <div class="about">
    <div>{{ obj }}</div>
    <button @click="change1">change hello/hi</button>
    <button @click="change2">change world/universe</button>
    <button @click="change3">change !/?</button>
  </div>
</template>

<script setup lang="ts">
import { ref, watch } from 'vue';

const obj = ref({
  a: {
    b: {
      c: {
        d: "hello"
      }
    }
  },
  b: {
    c: {
      d: "world",
    }
  },
  c: {
    d: "!",
  }
});

function change1() {
  if (obj.value.a.b.c.d == 'hello') {
    obj.value.a.b.c.d = 'hi';
  } else {
    obj.value.a.b.c.d = 'hello';
  }
}

function change2() {
  if (obj.value.b.c.d == 'world') {
    obj.value.b.c.d = 'universe';
  } else {
    obj.value.b.c.d = 'world';
  }
}

function change3() {
  if (obj.value.c.d == '!') {
    obj.value.c.d = '?';
  } else {
    obj.value.c.d = '!';
  }
}

watch(() => obj.value, (newVal) => {
  console.log('obj changed depth 0');
}, { deep: false });

watch(() => obj.value, (newVal) => {
  console.log('obj changed depth 1');
}, { deep: 1 });

watch(() => obj.value, (newVal) => {
  console.log('obj changed depth 2');
}, { deep: 2 });

watch(() => obj.value, (newVal) => {
  console.log('obj changed depth 3');
}, { deep: 3 });

watch(() => obj.value, (newVal) => {
  console.log('obj changed depth 4');
}, { deep: 4 });

</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
