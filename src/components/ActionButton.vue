<template>
<button :class="['action-button', `action-button--${type}`]">
  <img :src="icon" :alt="`${text} icon`" class="action-icon" />
  <span class="action-text">{{ text }}</span>
</button>
</template>

<script>
export default {
name: 'ActionButton',
props: {
  type: String,
  icon: String,
  text: String,
},
};
</script>

<style scoped>
.action-button {
display: flex;
align-items: center;
gap: 9px;
padding: 0 8px;
width: 114px;
color: #fff;
border: none;
font-size: 12px;
cursor: pointer;
}

.action-button--send {
background-color: #5a78ff;
border-radius: 16px 0 0 0;
}

.action-button--request,
.action-button--scan {
background-color: #c6c6cb;
}

.action-button--scan {
border-radius: 0 16px 0 0;
}

.action-icon {
width: 44px;
height: 44px;
}
</style>