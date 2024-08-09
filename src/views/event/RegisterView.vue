<script setup lang="ts">
import { toRefs, defineProps } from 'vue'
import { type Event } from '@/types'
import { useRouter } from 'vue-router'

const props = defineProps<{
  event: Event
  id: String
}>()
//eslint-disable-next-line @typescript-eslint/no-unused-vars
const { event } = toRefs(props)
const router = useRouter()
const register = () => {
  // If tthe registeration API call successful
  // Push back to the event detajls view
  router.push({ name: 'event-detail-view'})
}
</script>

<template>
  <p>Register event here</p>
  <aside class="ai-send"></aside>
  <button @click="register">Register</button>
</template>