<script setup>
defineProps({
  image: {
    type: String,
    required: true,
  },
  title: {
    type: String,
    required: true,
  },
  teaser: {
    type: String,
    required: true,
  },
  numberOfWords: {
    type: Number,
    required: true,
  },
});
</script>
<template>
  <div class="newsfeed__item">
    <div class="newsfeed__image">
      <img :src="image" alt="" />
    </div>
    <div class="newsfeed__text">
      <h2 class="newsfeed__heading">
        {{ title }}
      </h2>
      <p class="newsfeed__teaser">
        {{ teaser }}
      </p>
      <p class="newsfeed__meta">{{ floor(numberOfWords / 300) }} Minuten Lesezeit</p>
    </div>
  </div>
</template>
