<template>
  <v-container class="py-8">
    <v-row>
      <v-col cols="12" class="mb-6">
        <h1 class="text-h3 text-center">{{ isHomePage ? 'Популярные предложения' : 'Каталог квартир' }}</h1>
      </v-col>
      
      <v-col 
        v-for="apartment in displayedApartments" 
        :key="apartment.id" 
        cols="12" 
        md="6" 
        lg="4"
      >
        <v-card elevation="4" height="100%">
          <v-img
            :src="apartment.image"
            height="250"
            cover
          ></v-img>
          
          <v-card-title>{{ apartment.title }}</v-card-title>
          
          <v-card-text>
            <div class="text-h5 mb-2">{{ apartment.price }} ₽</div>
            <div class="mb-2">{{ apartment.location }}</div>
            <div>{{ apartment.area }} м² • {{ apartment.rooms }} комн.</div>
          </v-card-text>
          
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn
              color="primary"
              variant="outlined"
              :to="`/apartment/${apartment.id}`"
            >
              Подробнее
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
      
      <v-col v-if="isHomePage" cols="12" class="text-center">
        <v-btn
          color="primary"
          size="large"
          to="/catalog"
        >
          Смотреть все предложения
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref, computed } from 'vue'
import { useRoute, useRouter } from 'vue-router'

const route = useRoute()
const router = useRouter()
const isHomePage = computed(() => route.path === '/')

const apartments = ref([
  {
    id: 1,
    title: 'Премиум апартаменты',
    price: '25 000 000',
    location: 'ул. Тверская, 1',
    area: 120,
    rooms: 3,
    image: 'https://images.unsplash.com/photo-1502672260266-1c1ef2d93688'
  },
  {
    id: 2,
    title: 'Современная студия',
    price: '12 500 000',
    location: 'Ленинградский пр-т, 15',
    area: 45,
    rooms: 1,
    image: 'https://images.unsplash.com/photo-1522708323590-d24dbb6b0267'
  },
  {
    id: 3,
    title: 'Семейные апартаменты',
    price: '18 750 000',
    location: 'Кутузовский пр-т, 25',
    area: 85,
    rooms: 2,
    image: 'https://images.unsplash.com/photo-1502005097973-6a7082348e28'
  },
  {
    id: 4,
    title: 'Пентхаус с террасой',
    price: '35 000 000',
    location: 'Новинский бульвар, 10',
    area: 150,
    rooms: 4,
    image: 'https://images.unsplash.com/photo-1502005229762-cf1b2da7c5d6'
  },
  {
    id: 5,
    title: 'Квартира в сталинке',
    price: '28 500 000',
    location: 'Гоголевский бульвар, 5',
    area: 110,
    rooms: 3,
    image: 'https://images.unsplash.com/photo-1502672260266-1c1ef2d93688'
  },
  {
    id: 6,
    title: 'Светлая квартира с панорамными окнами',
    price: '22 000 000',
    location: 'Фрунзенская наб., 30',
    area: 95,
    rooms: 2,
    image: 'https://images.unsplash.com/photo-1502005229762-cf1b2da7c5d6'
  }
])

const displayedApartments = computed(() => {
  return isHomePage.value ? apartments.value.slice(0, 3) : apartments.value
})

const showDetails = (apartmentId) => {
  router.push(`/apartments/${apartmentId}`)
}
</script> 