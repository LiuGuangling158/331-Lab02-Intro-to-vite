<script setup lang="ts">
import type { Event } from '@/types'

defineProps<{
  event: Event
}>()
</script>

<template>
  <div class="event-category-organizer">
    <div class="info-container">
      <span class="category">{{ event.category }}</span>
      <span class="organizer">{{ event.organizer }}</span>
    </div>
  </div>
</template>

<style scoped>
.event-category-organizer {
  width: 250px;
  margin-bottom: 18px;
}

.info-container {
  text-align: right;
}

.category,
.organizer {
  font-size: 14px; /* 相同的字体大小 */
  display: block; /* 使每个元素占一行 */
  margin-bottom: 4px;
}

.organizer {
  margin-bottom: 0;
}
</style>