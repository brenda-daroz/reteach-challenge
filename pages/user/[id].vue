<template>
  <article>
    <h1>User profile</h1>
    <p v-if="pending">Loading...</p>
    <div v-else>
      <p>Name: {{ userDetails?.name }}</p>
      <p>Email: {{ userDetails?.email }}</p>
    </div>
  </article>
</template>

<script setup lang="ts">
type UserDetails = {
  id: number;
  email: string;
  name: string;
};
const route = useRoute();
const { data: userDetails, pending } = await useFetch<UserDetails>(
  `https://jsonplaceholder.typicode.com/users/${route.params.id}`
);
</script>
