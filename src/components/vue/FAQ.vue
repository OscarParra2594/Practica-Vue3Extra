<script setup>
import { ref } from "vue";
const data = ["tema 1", "tema 2", "tema 3", "tema 4"];

const selectedIndex = ref(0);
function showInfo(i) {
  if (i == selectedIndex.value) {
    selectedIndex.value = -i
  } else {
    selectedIndex.value = i
  }

}
</script>

<template>
  <div class="bg-blue-500 p-2 max-w-60 mx-auto mt-12">
    <div v-for="(theme, i) in data" :key="i">
      <h1
        @click="showInfo(i)"
        class="bg-blue-300 text-white px-1 flex justify-between cursor-default hover:cursor-pointer select-none"
      >
        {{ theme }}
        <span class="font-bold cursor-pointer">
          {{ selectedIndex == i ? "-" : "+" }}
        </span>
      </h1>
      <div
        v-show="selectedIndex == i"
        class="bg-blue-50/50 text-black p-1 mt-1 cursor-default"
      >
        {{ theme }}
      </div>
    </div>
  </div>
</template>