<template>
  <article>
    <h1>User profile</h1>
    <p v-if="pending">Loading...</p>
    <div v-else>
      <p>{{ userDetails?.name }}</p>
      <p>{{ userDetails?.id }}</p>
    </div>
  </article>
</template>

<script setup lang="ts">
type UserDetails = {
  id: number;
  name: string
}
const route = useRoute()
const { data: userDetails, pending, error } = await useFetch<UserDetails>(`https://jsonplaceholder.typicode.com/users/${route.params.id}`)
console.log(userDetails.value?.id)
</script>

<style></style>
