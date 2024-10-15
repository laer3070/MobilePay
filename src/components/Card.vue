<script setup>
import { ref } from 'vue';

defineProps({
  title: String,
  description: String,
  imageUrl: String,
  tags: Array,
  likes: Number,
});

const isLiked = ref(false);

const toggleLike = () => {
  isLiked.value = !isLiked.value;
};
</script>

<template>
  <div class="card">
    <img :src="imageUrl" :alt="title" class="card-image">
    <div class="card-content">
      <h2 class="card-title">{{ title }}</h2>
      <p class="card-description">{{ description }}</p>
      <div class="card-tags">
        <span v-for="tag in tags" :key="tag" class="tag">{{ tag }}</span>
      </div>
      <div class="card-footer">
        <button @click="toggleLike" class="like-button" :class="{ 'liked': isLiked }">
          <span class="like-icon">❤</span>
          <span class="like-count">{{ likes + (isLiked ? 1 : 0) }}</span>
        </button>
        <button class="share-button">Share</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  background-color: #ffffff;
  border-radius: 12px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  width: 320px;
  margin: 20px;
  transition: transform 0.3s ease;
}

.card:hover {
  transform: translateY(-5px);
}

.card-image {
  width: 100%;
  height: 180px;
  object-fit: cover;
}

.card-content {
  padding: 20px;
}

.card-title {
  font-size: 1.5rem;
  font-weight: 600;
  margin-bottom: 10px;
  color: #2c3e50;
}

.card-description {
  font-size: 1rem;
  color: #34495e;
  margin-bottom: 15px;
  line-height: 1.5;
}

.card-tags {
  display: flex;
  flex-wrap: wrap;
  margin-bottom: 15px;
}

.tag {
  background-color: #ecf0f1;
  color: #7f8c8d;
  padding: 5px 10px;
  border-radius: 20px;
  font-size: 0.8rem;
  margin-right: 8px;
  margin-bottom: 8px;
}

.card-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.like-button, .share-button {
  background: none;
  border: none;
  cursor: pointer;
  font-size: 1rem;
  display: flex;
  align-items: center;
  color: #7f8c8d;
  transition: color 0.3s ease;
}

.like-button:hover, .share-button:hover {
  color: #e74c3c;
}

.like-button.liked {
  color: #e74c3c;
}

.like-icon {
  margin-right: 5px;
}

.like-count {
  font-weight: 600;
}
</style>