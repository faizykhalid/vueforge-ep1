<script setup lang="ts">
import { ref } from "vue";
import type { Board } from "@/types";
const boards = ref<Partial<Board>[]>([
  {
    id: "1",
    title: "My first Board",
    order: "[]",
    image: {
      downloadUrl: "https://picsum.photos/480/270?boards?=1",
    },
  },
  {
    id: "2",
    title: "My Second Board",
    order: "[]",
    image: {
      downloadUrl: "https://picsum.photos/480/270?boards?=2",
    },
  },
  {
    id: "3",
    title: "My Third Board",
    order: "[]",
    image: {
      downloadUrl: "https://picsum.photos/480/270?boards?=3",
    },
  },
]);
function createBoard() {
  const lastIndex = boards.value.length - 1;
  boards.value.splice(lastIndex, 0, boards.value[lastIndex]);
}
</script>
<template>
  <h1 class="text-3xl">Boards</h1>
  <div class="flex">
    <board-card v-for="board in boards" :key="board.id" :board="board" />
    <button class="text-gray-500" @click="createBoard()">
      <span>New Board &#43;</span>
    </button>
  </div>
</template>
