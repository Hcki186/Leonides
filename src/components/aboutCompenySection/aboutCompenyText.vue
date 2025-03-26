<script setup lang="ts">
import { reactive } from 'vue'

const sections = reactive([
  {
    title: 'INŠPIROVANÝ HISTÓRIOU',
    content: [
      'Staroveké Grécko, označované ako kolíska Európskej civilizácie. Najpokrokovejším objavom je <span class="highlight">Demokracia</span>, o ktorú sa usilujú všetky súčasné štátne zriadenia. Veľkým gréckym zázrakom je vznik <span class="highlight">filozofie</span>. Diela starovekých Grécky filozofov sú študnicou nevyčerpateľného poznania a inšpirácie. Boli položené základy dnešných disciplín ako fyzika, botanika, logika, rétorika a politické vedy.',
      'Veľký rozmach v stavebnom umení prinieslo pokroky ako vodovod, kanalizácia, či kúpele. Grécka lyrika, divadlo, skloštvo a olympiáda. Toto všetko malo byť zničené jediným národom, jedným kráľom <span class="highlight">Xerxesom, kráľom Perzskej ríše</span>. Mala to byť pomsta za porážku jeho otca spred desiatich rokov. Zhromaždil najväčšiu armádu tej doby s úmyslom podmaniť si celé Grécko.',
    ],
  },
  {
    title: 'VÍZIA A POSLANIE LEONIDES',
    content: [
      'Kráľ LEONIDAS sa svojou odvahou a vierou vzoprel otroctvu a tyranii Perzskej ríše, čím uchránil základné ľudské hodnoty ako je sloboda a demokracia. Svojím hrdinstvom ovplyvnil vývoj celej civilizácie až po dnes. Inšpirovaný históriou sme sa my v spoločnosti <span class="highlight">LEONIDES - Transform your life</span> od svojho vzniku zaviazali, že naším poslaním bude pozitívne transformovať ľudské životy. Našim klientom prinášame transparentné informácie pod, pokrývajú finančného trhu, o ktorých sa otvorene nehovorí. Reálne riešenia, výhodné produkty a zodpovedný prístup. <span class="highlight">Dávame šancu ľuďom</span>, ktorí chcú zmeniť svoj život k lepšiemu a získať ponuku obchodnej príležitosti a kompletný systém, ktorý ich privedie k úspechu.',
    ],
  },
  {
    title: 'HODNOTY',
    content: [
      'Transparentnosť',
      'Etika',
      'Odvaha',
      'Viera',
      'Vzdelávanie',
      'Tímovosť',
      'Presvedčenie',
    ],
  },
  {
    title: 'STABILITA A ZÁZEMIE SPOLOČNOSTI',
    content: [
      'Vznik od roku 2009',
      'Viac ako 10 rokov praxe v odbore',
      'Sme členom AFISP',
      'Povolenie NBS PAG',
      'Certifikát solventných firiem',
      'Ocenený TOP externý partner za roky 2014 - 2015',
    ],
  },
])
</script>

<template>
  <div class="container-md">
    <div v-for="section in sections" :key="section.title" class="mb-5">
      <h2 class="section-title" v-html="section.title"></h2>
      <p
        v-for="(paragraph, index) in section.content"
        :key="index"
        class="section-text"
        v-html="paragraph"
      ></p>
    </div>
  </div>
</template>
