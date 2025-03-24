<template>
  <v-footer class="text-center d-flex flex-column py-4" color="primary">
    <v-container>
      <v-row>
        <v-col cols="12" md="4">
          <h3 class="text-h6 mb-4">О компании</h3>
          <p class="text-body-2">
            Мы специализируемся на продаже элитной недвижимости в лучших районах города. 
            Наша команда профессионалов поможет вам найти идеальное жилье.
          </p>
        </v-col>

        <v-col cols="12" md="4">
          <h3 class="text-h6 mb-4">Контакты</h3>
          <div class="text-body-2 mb-2">
            <v-icon start icon="mdi-phone" />
            +7 (999) 123-45-67
          </div>
          <div class="text-body-2 mb-2">
            <v-icon start icon="mdi-email" />
            info@elite-apartments.ru
          </div>
          <div class="text-body-2">
            <v-icon start icon="mdi-map-marker" />
            г. Москва, ул. Примерная, д. 1
          </div>
        </v-col>

        <v-col cols="12" md="4">
          <h3 class="text-h6 mb-4">Мы в соцсетях</h3>
          <div class="d-flex justify-center gap-2">
            <v-btn v-for="icon in icons" 
                   :key="icon" 
                   :icon="icon" 
                   variant="text"
                   size="large">
            </v-btn>
          </div>
        </v-col>
      </v-row>

      <v-row class="mt-6">
        <v-col cols="12">
          <v-divider class="mb-4"></v-divider>
          <div class="text-caption">
            © {{ new Date().getFullYear() }} — Элитная Недвижимость. Все права защищены.
          </div>
        </v-col>
      </v-row>
    </v-container>
  </v-footer>
</template>

<script setup>
const icons = [
  'mdi-facebook',
  'mdi-twitter',
  'mdi-linkedin',
  'mdi-instagram',
  'mdi-telegram'
]
</script>

<style scoped>
.v-footer {
  margin-top: auto;
  background: rgba(0, 0, 0, 0.8) !important;
  color: white;
}
</style>