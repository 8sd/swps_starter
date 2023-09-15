<script setup>
const props = defineProps({
  user: Object
})
</script>

<template>
  <v-card theme="dark">
    <div class="d-flex flex-no-wrap justify-space-between">
      <div>
        <v-card-title class="text-h5">
          {{ user.firstName }} {{ user.lastName }}
        </v-card-title>

        <v-card-subtitle>{{ user.company.title }}</v-card-subtitle>
      </div>

      <v-avatar class="ma-3" size="125" rounded="0">
        <v-img :src="user.image"></v-img>
      </v-avatar>
    </div>
  </v-card>
</template>

<style scoped>
p {
  font-family: sans
}
</style>