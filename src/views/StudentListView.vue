<script setup lang="ts">
import StudentCard from '@/components/StudentCard.vue'
import Student from '@/types/Student'
import { ref, onMounted } from 'vue'
import StudentService from '@/services/StudentService'

const students = ref<Student[]>(null)

onMounted(() => {
  StudentService.getStudents()
    .then((response) => {
      students.value = response.data
    })
    .catch(error => {
      console.error('There was an error!', error)
    })
})
</script>

<template>
  <h1>Students GPA</h1>
  <!-- Nnew element -->
  <div class="students">
    <StudentCard v-for="student in students" :key="student.id" :student="student"/>
  </div>
</template>

<style scoped>
.students {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>