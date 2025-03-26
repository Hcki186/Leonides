<script setup lang="ts">
const items = [
  {
    title: 'INŠPIROVANÝ HISTÓRIOU',
    image: new URL('@/assets/menu/menu-about-1.jpg', import.meta.url).href,
  },
  {
    title: 'VÍZIA A POSLANIE',
    image: new URL('@/assets/menu/menu-about-2.jpg', import.meta.url).href,
  },
  {
    title: 'HODNOTY LEONIDES',
    image: new URL('@/assets/menu/menu-about-3.jpg', import.meta.url).href,
  },
]

const splitTitle = (title: string): [string, string] => {
  const words = title.split(' ')
  if (words.length === 3) {
    return [words[0], `${words[1]} ${words[2]}`]
  }
  return [words[0], words[1] || '']
}
</script>

<template>
  <div class="container-md">
    <div class="grid-container">
      <div v-for="(item, index) in items" :key="index" class="grid-item">
        <h1>
          <span>{{ splitTitle(item.title)[0] }}</span>
          <span>{{ splitTitle(item.title)[1] }}</span>
        </h1>
        <div class="underline"></div>
        <div class="image-container">
          <img :src="item.image" alt="Grid image" />
          <div class="triangle"></div>
        </div>
      </div>
    </div>
  </div>
</template>
