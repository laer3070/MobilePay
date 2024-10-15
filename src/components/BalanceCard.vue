<script setup>
import { ref } from 'vue';

const balance = ref(1234.56);
</script>

<template>
  <div class="balance-card">
    <h2>Saldo</h2>
    <p class="balance">{{ balance.toFixed(2) }} kr.</p>
    <div class="actions">
      <button class="action-btn transfer">Overfør</button>
      <button class="action-btn request">Anmod</button>
    </div>
  </div>
</template>

<style scoped>
.balance-card {
  background-color: #0066FF;
  color: white;
  padding: 24px;
  border-radius: 16px;
  margin: 16px;
}

h2 {
  font-size: 16px;
  font-weight: 500;
  margin: 0 0 8px 0;
}

.balance {
  font-size: 32px;
  font-weight: 700;
  margin: 0 0 24px 0;
}

.actions {
  display: flex;
  gap: 12px;
}

.action-btn {
  flex: 1;
  padding: 12px;
  border-radius: 8px;
  font-size: 16px;
  font-weight: 600;
  border: none;
  cursor: pointer;
}

.transfer {
  background-color: white;
  color: #0066FF;
}

.request {
  background-color: transparent;
  border: 2px solid white;
  color: white;
}
</style>