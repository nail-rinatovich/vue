<template>
  <v-app>
    <BackgroundComponent>
      <MenuComponent />
      <v-main>
        <router-view></router-view>
      </v-main>
      <Datepicker />
      <Rating />
      <FooterComponent />
    </BackgroundComponent>
  </v-app>
</template>

<script setup>
import FooterComponent from './components/footer.vue'
import MenuComponent from './components/Menu.vue'
import BackgroundComponent from './components/Background.vue'
import ApartmentsList from './components/ApartmentsList.vue'
import Datepicker from './components/Datepicker.vue'
import Rating from './components/Rating.vue'
</script>
