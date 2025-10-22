<script setup lang="ts">
import type { Student } from '@/types'

const props = defineProps<{
  student: Student
}>()
</script>

<template>
  <div class="student-card">
    <div class="student-name">{{ student.name }} {{ student.surname }}</div>
    <div class="student-gpa">GPA: {{ student.gpa.toFixed(2) }}</div>
  </div>
</template>

<style scoped>
.student-card {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 16px;
  margin: 8px;
  background-color: #f9f9f9;
  min-width: 250px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.student-name {
  font-size: 18px;
  font-weight: bold;
  margin-bottom: 8px;
}

.student-gpa {
  font-size: 16px;
  color: #555;
}
</style>