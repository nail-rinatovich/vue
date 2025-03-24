<template>
  <v-container class="py-8">
    <v-card class="mx-auto pa-4" max-width="800" elevation="4">
      <v-card-title class="text-h4 mb-4">Свяжитесь с нами</v-card-title>
      <v-card-text>
        <v-form @submit.prevent="submitForm">
          <v-text-field
            v-model="form.name"
            label="Ваше имя"
            required
          ></v-text-field>
          
          <v-text-field
            v-model="form.email"
            label="Email"
            type="email"
            required
          ></v-text-field>
          
          <v-textarea
            v-model="form.message"
            label="Сообщение"
            required
          ></v-textarea>
          
          <v-btn type="submit" color="primary" block>
            Отправить сообщение
          </v-btn>
        </v-form>
      </v-card-text>
    </v-card>
  </v-container>
</template>

<script setup>
import { reactive } from 'vue'

const form = reactive({
  name: '',
  email: '',
  message: ''
})

const submitForm = () => {
  // Здесь будет логика отправки формы
  console.log('Form submitted:', form)
  alert('Спасибо за сообщение! Мы свяжемся с вами в ближайшее время.')
}
</script> 