<script setup lang="ts">
import Sidebar from './components/sections/sideMenu.vue'
import welcomeSection from './components/sections/welcomeSection.vue'
import aboutCompeny from './components/sections/aboutCompeny.vue'
import imagesSection from './components/sections/imagesSection.vue'
import companyName from './components/sections/companyName.vue'
import peopleNeeds from './components/sections/peopleNeeds.vue'
import googleMaps from './components/sections/googleMaps.vue'
import backGround from './components/sections/backGround.vue'
import contactMenu from './components/sections/contactMenu.vue'
</script>

<template>
  <div>
    <Sidebar />
    <welcomeSection />
    <aboutCompeny />
    <imagesSection />
    <companyName />
    <peopleNeeds />
    <googleMaps />
    <backGround />
    <contactMenu />
  </div>
</template>
