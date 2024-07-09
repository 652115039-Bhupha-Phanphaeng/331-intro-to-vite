<script setup lang="ts">
import { ref } from 'vue'
import Student from '@/types/Student'
defineProps<{
  student: Student
}>()
// const event = ref({
//   id: 59281101,
//   category: 'animal welfare',
//   title: 'Cat Adoption Day',
//   description: 'Find your new feline friend at this event.',
//   location: 'Meow Town',
//   date: '2January 28, 2022',
//   time: '12:00 AM',
//   petsAllowed: true,
//   organizer: 'Kat Laydee',
// })
</script>

<template>
  <div class="student-class">
    <div class="student-card">
      <h2>{{ student.name }} {{ student.surname }}</h2>
      <span>Grade: {{ student.gpa }}</span>
    </div>
  </div>
</template>

<style scoped>
.student-class {
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
}
.student-class:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px rgba(0, 0, 0, 0.2);
}
</style>
