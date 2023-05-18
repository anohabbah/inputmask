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

const a1: boolean | null | undefined = undefined
const a2: boolean | null | undefined = null
const bool = a1 && a2
</script>

<template>
  <ElInput ref="input" type="text" />
</template>
