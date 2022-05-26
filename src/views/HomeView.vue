<template>
  <v-sheet
    height="2500"
    color="black"
    class="d-flex align-center justify-center"
  >
    <v-card
      v-motion-slide-visible-once-right
      width="400"
      height="400"
      class="d-flex justify-center align-center target"
    >
      <v-card-title>
        {{ people.name }}
      </v-card-title>
    </v-card>
  </v-sheet>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const people = ref({ name: "CODMA", age: 25 });

    const vCardMotion = {
      initial: {
        opacity: 0,
        y: 100,
      },
      visible: {
        opacity: 1,
        y: 0,
      },
    };

    return { people, vCardMotion };
  },
};
</script>
