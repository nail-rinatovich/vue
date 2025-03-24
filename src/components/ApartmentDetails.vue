<template>
  <v-container class="py-8">
    <v-row v-if="apartment">
      <v-col cols="12" md="8">
        <v-img
          :src="apartment.image"
          height="400"
          cover
          class="rounded-lg"
        ></v-img>
        
        <h1 class="text-h3 mt-6 mb-4">{{ apartment.title }}</h1>
        
        <v-row class="mb-6">
          <v-col cols="12" sm="6">
            <div class="text-h4 mb-2">{{ apartment.price }} ₽</div>
            <div class="text-body-1 mb-2">{{ apartment.location }}</div>
            <div class="text-body-1">{{ apartment.area }} м² • {{ apartment.rooms }} комн.</div>
          </v-col>
          <v-col cols="12" sm="6">
            <div class="text-body-1 mb-2">
              <strong>Особенности:</strong> {{ apartment.features }}
            </div>
            <div class="text-body-1 mb-2">
              <strong>Ремонт:</strong> {{ apartment.renovation }}
            </div>
            <div class="text-body-1">
              <strong>Этаж:</strong> {{ apartment.floor }}
            </div>
          </v-col>
        </v-row>

        <div class="text-body-1 mb-4">
          <h2 class="text-h5 mb-2">Описание</h2>
          <p>{{ apartment.description }}</p>
        </div>

        <div class="text-body-1">
          <h2 class="text-h5 mb-2">Дополнительная информация</h2>
          <p>{{ apartment.additionalInfo }}</p>
        </div>
      </v-col>
      
      <v-col cols="12" md="4">
        <v-card class="pa-4">
          <h2 class="text-h5 mb-4">Связаться с агентом</h2>
          <v-form>
            <v-text-field
              label="Ваше имя"
              variant="outlined"
              full-width
              class="mb-4"
            ></v-text-field>
            <v-text-field
              label="Телефон"
              variant="outlined"
              full-width
              class="mb-4"
            ></v-text-field>
            <v-textarea
              label="Сообщение"
              variant="outlined"
              full-width
              class="mb-4"
            ></v-textarea>
            <v-btn
              color="primary"
              size="large"
              block
            >
              Отправить заявку
            </v-btn>
          </v-form>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()
const apartment = ref(null)

const apartmentsData = [
  {
    id: 1,
    title: 'Премиум апартаменты',
    price: '25 000 000',
    location: 'ул. Тверская, 1',
    area: 120,
    rooms: 3,
    image: 'https://images.unsplash.com/photo-1502672260266-1c1ef2d93688',
    features: 'Панорамные окна, высокие потолки, встроенная кухня',
    renovation: 'Дизайнерский ремонт 2023 года',
    floor: '15/25',
    description: 'Просторные апартаменты с панорамным видом на город. Современный дизайн интерьера, высокие потолки и большие окна создают ощущение простора и света. Кухня-гостиная оборудована встроенной техникой премиум-класса.',
    additionalInfo: 'В здании есть подземный паркинг, круглосуточная охрана, консьерж. Рядом находятся лучшие рестораны, театры и музеи города.'
  },
  {
    id: 2,
    title: 'Современная студия',
    price: '12 500 000',
    location: 'Ленинградский пр-т, 15',
    area: 45,
    rooms: 1,
    image: 'https://images.unsplash.com/photo-1522708323590-d24dbb6b0267',
    features: 'Смарт-дом, встроенная техника, гардеробная',
    renovation: 'Евроремонт 2022 года',
    floor: '8/20',
    description: 'Стильная студия с продуманной планировкой и современными технологиями. Встроенная система умного дома позволяет управлять освещением, климатом и безопасностью со смартфона.',
    additionalInfo: 'В комплексе есть фитнес-центр, супермаркет и кафе. Отличная транспортная доступность.'
  },
  {
    id: 3,
    title: 'Семейные апартаменты',
    price: '18 750 000',
    location: 'Кутузовский пр-т, 25',
    area: 85,
    rooms: 2,
    image: 'https://images.unsplash.com/photo-1502005097973-6a7082348e28',
    features: 'Детская комната, балкон, встроенные шкафы',
    renovation: 'Капитальный ремонт 2023 года',
    floor: '5/12',
    description: 'Уютная квартира для семьи с детьми. Отдельная детская комната, просторная гостиная и кухня. Встроенные шкафы-купе во всех комнатах.',
    additionalInfo: 'Во дворе детская площадка и парковка. Рядом школа и детский сад.'
  },
  {
    id: 4,
    title: 'Пентхаус с террасой',
    price: '35 000 000',
    location: 'Новинский бульвар, 10',
    area: 150,
    rooms: 4,
    image: 'https://images.unsplash.com/photo-1502005229762-cf1b2da7c5d6',
    features: 'Частная терраса, камин, винный погреб',
    renovation: 'Эксклюзивный ремонт 2023 года',
    floor: '25/25',
    description: 'Роскошный пентхаус с частной террасой и панорамным видом на город. Просторная гостиная с камином, отдельная кухня-столовая, винный погреб.',
    additionalInfo: 'В здании есть консьерж-сервис, подземный паркинг на 2 машины, лифт до квартиры.'
  },
  {
    id: 5,
    title: 'Квартира в сталинке',
    price: '28 500 000',
    location: 'Гоголевский бульвар, 5',
    area: 110,
    rooms: 3,
    image: 'https://images.unsplash.com/photo-1502672260266-1c1ef2d93688',
    features: 'Высокие потолки, лепнина, паркет',
    renovation: 'Реставрация 2022 года',
    floor: '4/7',
    description: 'Аутентичная квартира в сталинском доме с сохранением исторических деталей. Высокие потолки, лепнина, паркетные полы. Современные коммуникации.',
    additionalInfo: 'Дом является объектом культурного наследия. Рядом исторический центр города.'
  },
  {
    id: 6,
    title: 'Светлая квартира с панорамными окнами',
    price: '22 000 000',
    location: 'Фрунзенская наб., 30',
    area: 95,
    rooms: 2,
    image: 'https://images.unsplash.com/photo-1502005229762-cf1b2da7c5d6',
    features: 'Панорамные окна, встроенная кухня, гардеробная',
    renovation: 'Современный ремонт 2023 года',
    floor: '12/20',
    description: 'Светлая квартира с панорамными окнами и видом на реку. Современный дизайн с акцентом на естественное освещение.',
    additionalInfo: 'В комплексе есть подземный паркинг, фитнес-центр и ресторан. Рядом набережная и парк.'
  }
]

onMounted(() => {
  const id = parseInt(route.params.id)
  apartment.value = apartmentsData.find(apt => apt.id === id)
})
</script> 