<script setup>
defineProps({
  label: String,
  width: String,
  height: String,
})
</script>

<template>
  <v-btn :width="width" :height="height">{{ label }} </v-btn>
</template>

<style scoped>
.v-btn {
  background-color: #3a57e8;
  color: #ffffff;
  border-radius: 4px;
  text-transform: none;
  font-size: 16px;
}
</style>
