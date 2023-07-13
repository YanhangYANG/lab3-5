<template>
  <RouterLink class="event-link" :to="{name: 'event-detail', params:{id: event?.id}}">
    <div class="event-class">
      <div class="event-card">
        <span>Passenger id:{{ event?.id }}</span>
        <h4>Name:{{ event?.first_name }} {{ event?.last_name }} </h4>
        <h4>Gender:{{ event?.gender }}</h4>
        <h4>_____________________________</h4>
        <strong>Click to check details</strong>
      </div>
    </div>
  </RouterLink>
</template>

<script setup lang="ts">
import type { EventItem } from '../type'
import type { PropType } from 'vue'
const props = defineProps({
  event: {
    type: Object as PropType<EventItem>,
    required: true
  }
})
</script>

<style scoped>
.event-card {
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
}

.event-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px rgba(0, 0, 0, 0.2);
}
.event-link{
  color: #2c3e50;
  text-decoration: none;
}
</style>
