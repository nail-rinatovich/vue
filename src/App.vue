<template>
  <v-app>
    <BackgroundComponent>
      <MenuComponent />
      <v-main>
        <router-view></router-view>
      </v-main>
      <FooterComponent />
    </BackgroundComponent>
  </v-app>
</template>

<script setup>
import FooterComponent from './components/footer.vue'
import MenuComponent from './components/Menu.vue'
import BackgroundComponent from './components/Background.vue'
import ApartmentsList from './components/ApartmentsList.vue'
</script>
