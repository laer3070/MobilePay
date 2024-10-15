<template>
  <div class="user-favorite">
    <div class="user-initials">{{ initials }}</div>
    <div class="user-name">
      <div>{{ firstName }}</div>
      <div>{{ lastName }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'UserFavorite',
  props: {
    initials: String,
    firstName: String,
    lastName: String,
  },
};
</script>

<style scoped>
.user-favorite {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 60px;
}

.user-initials {
  background-color: #dfe2f5;
  color: #5a78ff;
  border-radius: 30px;
  width: 60px;
  height: 60px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 27px;
  font-weight: 500;
}

.user-name {
  margin-top: 8px;
  text-align: center;
  font-size: 12px;
  color: #000;
}
</style>
