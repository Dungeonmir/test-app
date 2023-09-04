<template>
  <v-container>
    <game-end-dialog
      :dialog="isGameOver"
      @update:dialog="isGameOver = $event"
    ></game-end-dialog>
    <v-row>
      <v-col cols="12" md="6">
        <h2>{{ level }} Уровень</h2>
        <v-container d-flex align-center v-if="!isGameOver">
          <v-progress-linear
            rounded
            background-color="pink lighten-3"
            color="pink lighten-1"
            :value="(xp / maxXpArray[level]) * 100"
          ></v-progress-linear>
          <p class="ma-4 text-no-wrap">{{ xp }} / {{ maxXpArray[level] }}XP</p>
        </v-container>

        <h3>Золото: {{ gold }}$</h3>
        <h3>Сила: {{ speedXp }}</h3>
        <v-container d-flex flex-column>
          <v-btn @click="addXp" class="ma-2" v-if="!isGameOver"
            >Сразиться</v-btn
          >

          <v-btn @click="addSpeedXP" class="ma-2" v-if="!isGameOver"
            >Тренировка {{ speedXpPriceArray[speedXPLevel] }}$</v-btn
          >
        </v-container>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import GameEndDialog from "./GameEndDialog.vue";
export default {
  components: { GameEndDialog },
  data() {
    return {
      speedXp: 1,
      speedXpPriceArray: [2, 3, 5, 7, 10, 15, 20, 25, 30, 50, 70, 100],
      speedXPLevel: 0,
      maxXpArray: [3, 5, 7, 10, 15, 25, 40, 50, 70, 100],
      xp: 0,
      level: 0,
      isGameOver: false,
      showEndDialog: false,
      gold: 0,
    };
  },
  watch: {
    xp: function (val) {
      if (this.xp >= this.maxXpArray[this.level]) {
        this.level++;
        this.xp = 0;
      }
      console.log(val);
    },
    level: function (val) {
      if (this.level == 10) {
        this.isGameOver = true;
      }
      this.gold += this.getRandomInt(this.level) + 1;
    },
    isGameOver: function (val) {},
  },
  methods: {
    addXp() {
      this.xp += this.speedXp;
    },
    addSpeedXP() {
      if (this.gold >= this.speedXpPriceArray[this.speedXPLevel]) {
        this.gold -= this.speedXpPriceArray[this.speedXPLevel];
        this.speedXp++;
        this.speedXPLevel++;
      }
    },
    getRandomInt(max) {
      return Math.floor(Math.random() * max);
    },
  },
};
</script>
