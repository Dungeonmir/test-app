<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="p-4 justify-center">
        <v-carousel show-arrows-on-hover hide-delimiters>
          <v-carousel-item
            src="https://i.ibb.co/Pxfj3qR/photo-2022-09-18-16-40-02.jpg"
            cover
          ></v-carousel-item>

          <v-carousel-item
            src="https://i.ibb.co/6wH4HBV/photo-2022-09-18-16-40-05.jpg"
            cover
          ></v-carousel-item>

          <v-carousel-item
            src="https://i.ibb.co/xDp8Xfz/photo-2022-09-19-13-56-56.jpg"
            cover
          ></v-carousel-item>
        </v-carousel>
      </v-card>
      <div class="py-8">
        <h1 class="py-2">О программировании</h1>
        <p>
          Меня всегда привлекала возможность создавать что-то новое и полезное с
          помощью кода.
        </p>
        <p>
          Когда я столкнулся с веб-программированием, я испытал небольшой шок -
          результаты твоей работы видны сразу, небольшой код способен
          преобразить всю веб-страницу, результат твоей работы сразу доступен на
          всех платформах.
        </p>
        <p>
          Я считаю, что веб-программирование - это идеальное сочетание
          творчества и логики. Оно, как головоломка, которую никогда не удастся
          до конца решить, ведь всегда есть куда расти и что-то изучить.
        </p>
        <p>
          В общем, программирование для меня - это не просто работа, а настоящее
          хобби и призвание. Я не представляю себе другой профессии, которая бы
          меня так увлекала и приносила столько удовольствия каждый день.
        </p>
      </div>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: "IndexPage",
};
</script>
