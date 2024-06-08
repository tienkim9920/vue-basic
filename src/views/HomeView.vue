<script setup>
import { computed, onMounted, ref } from 'vue';

const users = ref([]);
const txtSearch = ref('');

onMounted(() => {
  (async () => {
    const res = await fetch('https://jsonplaceholder.typicode.com/users');
    const data = await res.json();
    users.value = data;
  })();
});

const filterUsers = computed(() => {
  return users.value.filter(item => item.name.toUpperCase().indexOf(txtSearch.value.toUpperCase()) !== -1 ||
    item.email.toUpperCase().indexOf(txtSearch.value.toUpperCase()) !== -1);
})
</script>

<template>
  <main style="color: #000; padding: 2rem;">
    <input type="text" placeholder="Enter Search Here!" v-model="txtSearch" />
    <div class="group-card">
      <div class="card-item" v-for="user in filterUsers">
        <h2>{{ user.name }}</h2>
        <i>{{ user.email }}</i>
      </div>
    </div>
  </main>
</template>

<style>
input {
  width: 100%;
  padding: .6rem 1.2rem;
  border-radius: 50px;
  border: none;
  outline: none;
  background: #ededed;
}

.group-card {
  margin-top: 1.5rem;
  display: flex;
  flex-direction: column;
  row-gap: 1.5rem;
}

.card-item {
  border-radius: 10px;
  background: #324558;
  color: #fff;
  cursor: pointer;
  padding: .8rem 1rem;
  box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.15);
}

.card-item:hover {
  background: #243241;
}
</style>