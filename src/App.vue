<script lang="ts" setup>
const SECOND = 1000

const now = ref(new Date())

const timeoutId = setInterval(() => {
  now.value = new Date()
}, SECOND)

onUnmounted(() => {
  clearInterval(timeoutId)
})
</script>

<template>
  <Box
    :padding="2"
    width="100%"
    maxWidth="100%"
    justifyContent="center"
    alignItems="center"
    borderColor="cyanBright"
    borderStyle="round"
  >
    <Text>{{ now.toLocaleTimeString() }}</Text>
  </Box>
</template>
