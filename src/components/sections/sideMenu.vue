<script setup lang="ts">
import { ref, onMounted } from 'vue'
import { useIntersectionObserver } from '@vueuse/core'

const items = [
  {
    title: 'O SPOLOČNOSTI',
    image: new URL('@/assets/menu/menu-need-2.jpg', import.meta.url).href,
  },
  {
    title: 'ČO PONÚKA LEONIDES?',
    image: new URL('@/assets/menu/menu-need-2.jpg', import.meta.url).href,
  },
  {
    title: 'POTREBY ĽUDÍ',
    image: new URL('@/assets/menu/menu-need-2.jpg', import.meta.url).href,
  },
  {
    title: 'ZMEŇ SVOJ ŽIVOT',
    image: new URL('@/assets/menu/menu-need-2.jpg', import.meta.url).href,
  },
  {
    title: 'PARTNERI',
    image: new URL('@/assets/menu/menu-need-2.jpg', import.meta.url).href,
  },
  {
    title: 'KONTAKT',
    image: new URL('@/assets/menu/menu-need-2.jpg', import.meta.url).href,
  },
]

const isVisibleMenu = ref(Array(items.length).fill(false))
const menuOpen = ref(false)

onMounted(() => {
  const sideMenu = document.querySelectorAll('.grid-item-menu') as NodeListOf<HTMLElement>
  sideMenu.forEach((item, index) => {
    useIntersectionObserver(item, ([{ isIntersecting }]) => {
      if (isIntersecting) {
        isVisibleMenu.value[index] = true
      }
    })
  })
})

const toggleMenu = () => {
  menuOpen.value = !menuOpen.value
}
</script>

<template>
  <div class="side-menu">
    <button v-if="!menuOpen" class="btn menu-button" @click="toggleMenu">
      <img src="@/assets/elements/images/menu.svg" alt="" />
    </button>
    <div
      class="offcanvas offcanvas-start custom-offcanvas"
      :class="{ show: menuOpen }"
      tabindex="-1"
    >
      <div class="offcanvas-header">
        <h5 class="offcanvas-title">MENU</h5>
        <img
          src="@/assets/elements/images/menu-rot.svg"
          class="menu-rot"
          @click="toggleMenu"
          alt=""
        />
      </div>
      <div class="offcanvas-body">
        <div class="needs-grid">
          <div
            v-for="(item, index) in items"
            :key="index"
            class="grid-item-menu"
            :class="{ visible: isVisibleMenu[index] }"
          >
            <div class="image-container">
              <div class="image-border">
                <img class="need-image" :src="item.image" :alt="item.title" />
              </div>
            </div>
            <div class="need-info">
              <span class="need-number">{{ index + 1 }}</span>
              <div class="underline"></div>
              <p class="need-title">{{ item.title }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
