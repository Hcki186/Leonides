<script setup lang="ts">
const needsItems = [
  { title: 'DETI', image: new URL('@/assets/menu/menu-need-1.jpg', import.meta.url).href },
  { title: 'BÝVANIE', image: new URL('@/assets/menu/menu-need-2.jpg', import.meta.url).href },
  { title: 'SPORENIE', image: new URL('@/assets/menu/menu-need-3.jpg', import.meta.url).href },
  { title: 'DÔCHODOK', image: new URL('@/assets/menu/menu-need-4.jpg', import.meta.url).href },
]
</script>

<template>
  <div class="container">
    <div class="needs-grid">
      <div v-for="(need, index) in needsItems" :key="index" class="need-card">
        <h1>{{ need.title }}</h1>
        <div class="underline"></div>
        <div class="image-wrapper">
          <div class="image-border"></div>
          <img
            class="circle-bg"
            src="@/assets/elements/images/circle.svg"
            alt="Circle background"
          />
          <img class="need-image" :src="need.image" :alt="need.title" />
        </div>
      </div>
    </div>
  </div>
</template>
