<template>
  <AwesomeSection>
    <h2>Users List</h2>
    <p v-if="pending">Loading...</p>
    <div v-else>
      <input type="text" placeholder="Search..." v-model="search" />
      <ul v-for="user in filteredUsers" :key="user.id">
        <NuxtLink :to="`/user/${user.id}`" tag="li">
          <p>Name: {{ user.name }}</p>
          <p>Email: {{ user.email }}</p>
          <p>Username: {{ user.username }}</p>
          <hr />
        </NuxtLink>
      </ul>
    </div>
  </AwesomeSection>
</template>

<script setup lang="ts">
import { ref, computed } from "vue";

const search = ref("");

interface User {
  id: number;
  name: string;
  email: string;
  username: string;
}

const filteredUsers = computed(() =>
  users.value
    ? users.value.filter((user: User) =>
        user.name.toLowerCase().includes(search.value.toLowerCase())
      )
    : []
);

const { data: users, pending } = await useFetch<User[]>(
  "https://jsonplaceholder.typicode.com/users"
);
</script>
