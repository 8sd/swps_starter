<script setup>
const props = defineProps({
  id: Number
})
const { data: users, pending, error } = await useFetch(() => `https://dummyjson.com/users/?limit=10`)
console.log(users)
</script>

<template>
    <p v-if="pending">Fetching...</p>
    <pre v-else-if="error">Could not load: {{ error.data }}</pre>
    <div v-else>
      <v-container>
        <v-row>
          <v-col
            v-for="user in users.users"
            :key="user.id"
          >
            <User :user="user"></User>
          </v-col>
        </v-row>
      </v-container>
    </div>
</template>

<style scoped>
</style>