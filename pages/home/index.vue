<template>
  <ZeroLoading v-if="loading" type="wobble"></ZeroLoading>
</template>

<script setup>
import { ref } from 'vue'
import ZeroLoading from '../../packages/components/zero-loading/zero-loading.vue'

console.log(global[Symbol.for('api')])

const { a, b } = global[Symbol.for('api')]

a()
b()

const loading = ref(true)
</script>

<style lang="scss" scoped></style>
