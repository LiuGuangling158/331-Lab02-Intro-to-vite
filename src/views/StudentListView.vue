<script setup lang="ts">
import { ref, onMounted } from 'vue'
import StudentCard from '@/components/StudentCard.vue'
import type { Student } from '@/types'
import StudentService from '@/services/StudentService'

const students = ref<Student[]>([])

onMounted(() => {
  StudentService.getStudents()
    .then((response) => {
      console.log('Student data fetched:', response.data)
      students.value = response.data
    })
    .catch((error) => {
      console.error('Error fetching student data:', error)
    })
})
</script>

<template>
  <div class="student-list-container">
    <h1>Student Information</h1>
    <div class="students-grid" v-if="students.length > 0">
      <StudentCard 
        v-for="(student, index) in students" 
        :key="index" 
        :student="student" 
      />
    </div>
    <div v-else class="loading-message">Loading student data...</div>
  </div>
</template>

<style scoped>
.student-list-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

h1 {
  text-align: center;
  margin-bottom: 30px;
}

.students-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 20px;
}

.loading-message {
  text-align: center;
  font-size: 18px;
  color: #666;
  margin-top: 50px;
}
</style>