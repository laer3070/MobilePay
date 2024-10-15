<template>
  <div :class="['nav-item', { 'nav-item--active': active }]">
    <img :src="icon" :alt="`${text} icon`" class="nav-icon" />
    <span class="nav-text">{{ text }}</span>
  </div>
</template>

<script>
export default {
  name: 'NavItem',
  props: {
    icon: String,
    text: String,
    active: Boolean,
  },
};
</script>

<style scoped>
.nav-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  color: #999;
}

.nav-item--active {
  color: #3a3244;
}

.nav-icon {
  width: 32px;
  height: 32px;
}

.nav-text {
  margin-top: 4px;
  font-size: 10px;
}
</style>
