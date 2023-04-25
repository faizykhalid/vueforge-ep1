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
</script>
<template>
  <h1 class="text-3xl">Boards</h1>
  <board-card v-for="board in boards" :key="board.id" :board="board" />
  <!-- <button class="text-gray-500" @click="createBoard(newBoardTemplate)">
    <span>New Board +</span>
  </button> -->
</template>
