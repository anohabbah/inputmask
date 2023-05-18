<script setup lang="ts">
defineOptions({
  name: 'IndexPage',
})

const maskForm = reactive({
  model: '',
  email: '',
  insee: '',
})
</script>

<template>
  <div>
    <InputMask v-model="maskForm.model" mask="99 99 999 999" />
    <InputMask v-model="maskForm.email" mask="email" placeholder="example@email.com" class="mt-8" />
    <InputMask v-model="maskForm.insee" mask="insee" placeholder="Numéro de sécurité social" class="mt-8" />
  </div>
</template>

<route lang="yaml">
meta:
  layout: home
</route>
