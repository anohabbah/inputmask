<script setup lang="ts">
import Inputmask from 'inputmask'

const { mask } = defineProps<{ mask: '9' | 'a' | '*' | string }>()

const input = ref()

Inputmask.extendAliases({
  insee: { mask: '9 99 99 99999 999' },
})

onMounted(() => {
  const masker = new Inputmask(mask)
  masker.mask(input.value?.$refs.input)
})
</script>

<template>
  <ElInput ref="input" type="text" />
</template>
