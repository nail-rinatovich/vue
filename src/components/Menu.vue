<template>
  <v-app-bar color="primary" prominent>
    <v-app-bar-title>
      <router-link to="/" class="text-white text-decoration-none">
        Элитная Недвижимость
      </router-link>
    </v-app-bar-title>

    <v-spacer></v-spacer>

    <router-link to="/" custom v-slot="{ navigate }">
      <v-btn variant="text" @click="navigate">Главная</v-btn>
    </router-link>
    
    <router-link to="/catalog" custom v-slot="{ navigate }">
      <v-btn variant="text" @click="navigate">Каталог</v-btn>
    </router-link>
    
    <router-link to="/about" custom v-slot="{ navigate }">
      <v-btn variant="text" @click="navigate">О нас</v-btn>
    </router-link>
    
    <router-link to="/contacts" custom v-slot="{ navigate }">
      <v-btn variant="text" @click="navigate">Контакты</v-btn>
    </router-link>
  </v-app-bar>
</template>