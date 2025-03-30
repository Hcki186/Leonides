<script setup lang="ts">
import { reactive } from 'vue'

const images = reactive([
  { src: new URL('@/assets/images/image01.jpg', import.meta.url).href, alt: 'Handshake' },
  { src: new URL('@/assets/images/image02.jpg', import.meta.url).href, alt: 'Writing on paper' },
  { src: new URL('@/assets/images/image03.jpg', import.meta.url).href, alt: 'Smiling coworkers' },
  {
    src: new URL('@/assets/images/image04.jpg', import.meta.url).href,
    alt: 'Laptop and documents',
  },
])
</script>

<template>
  <div class="imagesSection">
    <div class="images-section">
      <!-- Obrazok 01 -->
      <div class="image-container">
        <img :src="images[0].src" :alt="images[0].alt" class="image" />
        <div class="hover-overlay">
          <p class="hover-text">
            Zmeň svoj <br />
            <strong>život v spoločenskom postavení</strong>
          </p>
        </div>
      </div>

      <!-- Obrazok 02 s overlay -->

      <div class="image-container">
        <img :src="images[1].src" :alt="images[1].alt" class="image" />
        <div class="hover-overlay">
          <p class="hover-text">
            Zmeň svoj život <br />
            <strong>vo svojej kariére</strong>
          </p>
        </div>
      </div>

      <!-- Obrazok 03 -->
      <div class="image-container">
        <img :src="images[2].src" :alt="images[2].alt" class="image" />
        <div class="hover-overlay">
          <p class="hover-text">
            Zmeň svoj <br />
            <strong>vo vzdelávaní</strong>
          </p>
        </div>
      </div>

      <!-- Obrazok 04 -->
      <div class="image-container">
        <img :src="images[3].src" :alt="images[3].alt" class="image" />
        <div class="hover-overlay">
          <p class="hover-text">
            Zmeň svoj <br />
            <strong>s finančnou nezávislosťou</strong>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>
