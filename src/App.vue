<script setup lang="ts">
import axios from "axios";
import type { AxiosResponse } from "axios";
import { ref } from "vue";

const corps = ref("")
axios
  .get("http://localhost:3000/")
  .then(
    (response: AxiosResponse) => {corps.value = response.data["message"]}
  )

</script>

<template>
  <h1>Hi!</h1>
  <p>{{ corps }}</p>
</template>

<style scoped>
</style>