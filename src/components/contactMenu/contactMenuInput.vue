<script setup lang="ts">
import { ref } from 'vue'

const form = ref({
  name: '',
  phone: '',
  email: '',
  message: '',
})

const errors = ref<FormErrors>({})

type FormErrors = {
  name?: string
  phone?: string
  email?: string
  message?: string
}

const submitForm = () => {
  errors.value = {} as FormErrors
  let valid = true

  if (!form.value.name) {
    errors.value.name = 'Meno je povinné'
    valid = false
  }
  if (!form.value.phone) {
    errors.value.phone = 'Telefón je povinný'
    valid = false
  }
  if (!form.value.email) {
    errors.value.email = 'E-mail je povinný'
    valid = false
  }
  if (!form.value.message) {
    errors.value.message = 'Odkaz je povinný'
    valid = false
  }

  if (valid) {
    console.log('Formulár odoslaný', form.value)
  }
}
</script>
<template>
  <div class="contact-menu-input">
    <div class="container">
      <div class="contact-form">
        <div class="inputs">
          <input v-model="form.name" type="text" placeholder="Meno" class="input" />
          <span v-if="errors.name" class="error">{{ errors.name }}</span>
          <input v-model="form.phone" type="text" placeholder="Telefón" class="input" />
          <span v-if="errors.phone" class="error">{{ errors.phone }}</span>
          <input v-model="form.email" type="email" placeholder="E-mail" class="input" />
          <span v-if="errors.email" class="error">{{ errors.email }}</span>
        </div>
        <input v-model="form.message" type="text" placeholder="Odkaz" class="input message" />
        <span v-if="errors.message" class="error">{{ errors.message }}</span>
      </div>
      <button class="submit" @click="submitForm">Odoslať</button>
    </div>
  </div>
</template>
