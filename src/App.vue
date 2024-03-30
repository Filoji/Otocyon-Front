<script setup lang="ts">
import axios from "axios";
import type { AxiosResponse } from "axios";
import { ref } from "vue";
import Form from "./components/Form.vue";

const corps = ref("Loading…")
async function main() {
  await axios
    .get("http://localhost:3000/")
    .then(
      (response: AxiosResponse) => { corps.value = response.data["message"] }
    )
    .catch(
      (error: unknown) => { console.log(error) }
    )
}
main();
</script>

<template>
  <h1>Hi!</h1>
  <p>{{ corps }}</p>
  <Form />
</template>

<style scoped></style>