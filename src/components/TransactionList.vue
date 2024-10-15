<script setup>
import { ref } from 'vue';

const transactions = ref([
  { id: 1, name: 'John Doe', amount: -50, date: '2023-05-15' },
  { id: 2, name: 'Jane Smith', amount: 75, date: '2023-05-14' },
  { id: 3, name: 'Grocery Store', amount: -30, date: '2023-05-13' },
]);
</script>

<template>
  <div class="transaction-list">
    <h2>Recent Activity</h2>
    <ul>
      <li v-for="transaction in transactions" :key="transaction.id">
        <div class="transaction-info">
          <span class="name">{{ transaction.name }}</span>
          <span class="date">{{ transaction.date }}</span>
        </div>
        <span class="amount" :class="{ positive: transaction.amount > 0 }">
          {{ transaction.amount > 0 ? '+' : '' }}{{ transaction.amount }} kr.
        </span>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.transaction-list {
  padding: 24px;
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

.transaction-info {
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
</style>