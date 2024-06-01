<script setup>
import { useRoute } from 'vue-router';

const router = useRoute();
</script>

<template>
  <main style="color: #000;">
    Todo Item {{ router.params.id }}
  </main>
</template>
