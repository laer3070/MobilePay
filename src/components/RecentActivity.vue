<script setup>
import { ref } from 'vue';

const activities = ref([
  { id: 1, name: 'John Doe', amount: -50, date: '15. maj' },
  { id: 2, name: 'Jane Smith', amount: 75, date: '14. maj' },
  { id: 3, name: 'Grocery Store', amount: -30, date: '13. maj' },
]);
</script>

<template>
  <div class="recent-activity">
    <h2>Seneste aktivitet</h2>
    <ul>
      <li v-for="activity in activities" :key="activity.id">
        <div class="activity-info">
          <span class="name">{{ activity.name }}</span>
          <span class="date">{{ activity.date }}</span>
        </div>
        <span class="amount" :class="{ positive: activity.amount > 0 }">
          {{ activity.amount > 0 ? '+' : '' }}{{ activity.amount }} kr.
        </span>
      </li>
    </ul>
    <button class="view-all">Se alle transaktioner</button>
  </div>
</template>

<style scoped>
.recent-activity {
  padding: 24px 16px;
}

h2 {
  font-size: 20px;
  font-weight: 600;
  margin-bottom: 16px;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 0;
  border-bottom: 1px solid #E5E7EB;
}

.activity-info {
  display: flex;
  flex-direction: column;
}

.name {
  font-size: 16px;
  font-weight: 500;
}

.date {
  font-size: 14px;
  color: #6B7280;
}

.amount {
  font-size: 16px;
  font-weight: 600;
  color: #EF4444;
}

.amount.positive {
  color: #10B981;
}

.view-all {
  display: block;
  width: 100%;
  padding: 12px;
  margin-top: 16px;
  background-color: #F3F4F6;
  border: none;
  border-radius: 8px;
  color: #0066FF;
  font-weight: 600;
  cursor: pointer;
}
</style>