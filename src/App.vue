<script setup>
import { RouterLink } from 'vue-router';

</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="60" height="60" />
    <nav>
      <div class="btn-main">
        <RouterLink to="/">Home Todo</RouterLink>
      </div>
      <div class="btn-action">
        <RouterLink to="/create">Create Todo</RouterLink>
      </div>
    </nav>
  </header>

</template>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  padding: .4rem 2rem;
  align-items: center;
  box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.15);
}

nav {
  display: flex;
  column-gap: 1rem;
}
</style>
