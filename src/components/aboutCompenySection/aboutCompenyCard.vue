<script setup lang="ts">
import { ref, onMounted } from 'vue'
import { useIntersectionObserver } from '@vueuse/core'

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

const isVisible = ref(Array(items.length).fill(false))

onMounted(() => {
  const gridItems = document.querySelectorAll('.grid-item') as NodeListOf<HTMLElement>
  gridItems.forEach((item, index) => {
    useIntersectionObserver(item, ([{ isIntersecting }]) => {
      if (isIntersecting) {
        isVisible.value[index] = true
      }
    })
  })
})
</script>

<template>
  <div class="grid-container">
    <div
      v-for="(item, index) in items"
      :key="index"
      class="grid-item"
      :class="{ visible: isVisible[index] }"
    >
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
</template>
