<template>
  <v-dialog v-model="dialog" width="auto">
    <v-card>
      <v-card-title>Победа</v-card-title>
      <v-card-text> Вы достигли максимального уровня!</v-card-text>
      <v-card-actions>
        <v-btn color="primary" block @click="closeDialog">Закрыть</v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  name: "game-end-dialog",
  props: {
    dialog: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    closeDialog() {
      this.$emit("update:dialog", false);
    },
  },
};
</script>
