<script setup lang="ts">
import { ref } from 'vue';

export interface Props {
  mail: string
  size?: number
}

const props = withDefaults(defineProps<Props>(), {
  size: 200
})

async function hash(string: string) {
  const utf8 = new TextEncoder().encode(string);
  const hashBuffer = await crypto.subtle.digest('SHA-256', utf8);
  const hashArray = Array.from(new Uint8Array(hashBuffer));
  const hashHex = hashArray
    .map((bytes) => bytes.toString(16).padStart(2, '0'))
    .join('');
  return hashHex;
}

const url = ref("");

hash(props.mail)
  .then(
    (hex: string) => url.value = `https://gravatar.com/avatar/${hex}"?d=identicon&s=${props.size}`
  );
</script>

<template>
  <img :src="url" />
</template>