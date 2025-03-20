<script setup lang="ts">
import { ref } from 'vue'

const menuItems = ref([
  { text: 'O SPOLOČNOSTI', image: '/src/assets/menu/menu-need-2.jpg' },
  { text: 'ČO PONÚKA LEONIDES?', image: '/src/assets/menu/menu-need-2.jpg' },
  { text: 'POTREBY ĽUDÍ', image: '/src/assets/menu/menu-need-2.jpg' },
  { text: 'ZMEŇ SVOJ ŽIVOT', image: '/src/assets/menu/menu-need-2.jpg' },
  { text: 'PARTNERI', image: '/src/assets/menu/menu-need-2.jpg' },
  { text: 'KONTAKT', image: '/src/assets/menu/menu-need-2.jpg' },
])
</script>

<template>
  <div>
    <!-- Tlačidlo na otvorenie menu -->
    <button
      class="btn btn-primary menu-button"
      type="button"
      data-bs-toggle="offcanvas"
      data-bs-target="#sidebarMenu"
    >
      ☰ MENU
    </button>

    <!-- Sidebar (Offcanvas) s 50% šírkou -->
    <div class="offcanvas offcanvas-start custom-offcanvas" tabindex="-1" id="sidebarMenu">
      <div class="offcanvas-header">
        <h5 class="offcanvas-title">MENU</h5>
        <button type="button" class="btn-close" data-bs-dismiss="offcanvas"></button>
      </div>
      <div class="offcanvas-body">
        <!-- Grid layout pre ikony -->
        <div class="container">
          <div class="row text-center">
            <div class="col-6 col-md-4" v-for="(item, index) in menuItems" :key="index">
              <div class="menu-item">
                <img :src="item.image" alt="Menu Icon" class="menu-icon" />
                <p>{{ item.text }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
