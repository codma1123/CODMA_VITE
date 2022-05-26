<template>
  <v-sheet height="4500" color="black">
    <v-col cols="12">
      <v-card
        color="black"
        height="600"
        class="mx-auto d-flex justify-center align-center"
      >
        <div>
          <v-card-title
            class="animate__animated animate__bounceIn text-h4 font-weight-bold"
          >
            CODMA INFOMATION
          </v-card-title>
          <v-card-subtitle class="animate__animated animate__bounceIn">
            : animate.css + vuetify3 v-card-title
          </v-card-subtitle>
        </div>
      </v-card>
      <v-divider></v-divider>
      <v-card
        color="black"
        class="d-flex justify-center align-center white--text"
      >
        <v-btn icon color="black" class="mt-5" @click="toDown">
          <v-icon dark>mdi-chevron-double-down</v-icon>
        </v-btn>
      </v-card>
    </v-col>

    <v-col v-for="i in 7" :key="i" cols="12">
      <v-card color="black" height="100"> </v-card>
      <v-card
        :color="i === 1 ? 'black' : 'white'"
        class="mx-auto d-flex justify-center align-center"
        v-motion-slide-visible-right
        width="380"
        height="380"
        rounded="xl"
        outlined
        :style="vCardStyle"
      >
        <v-card-title v-if="i !== 1">
          {{ people.name }}
        </v-card-title>
        <div v-else>
          <v-card-title>
            <strong class="text-h5">스크롤</strong>해서 내용을 살펴보세요.
          </v-card-title>
          <v-card-subtitle>
            : vueuse/motion + vuetify3 v-card-title <br />
            ::-webkit-scrollbar
          </v-card-subtitle>
        </div>
      </v-card>
    </v-col>
  </v-sheet>

  <v-divider></v-divider>

  <v-footer>
    <v-card flat tile class="indigo lighten-1 white--text text-center">
      <v-card-text>
        <v-btn v-for="icon in icons" :key="icon" class="mx-4 white--text" icon>
          <v-icon size="24px">
            {{ icon.icon }}
          </v-icon>
        </v-btn>
      </v-card-text>

      <v-card-text class="white--text pt-0">
        Phasellus feugiat arcu sapien, et iaculis ipsum elementum sit amet.
        Mauris cursus commodo interdum. Praesent ut risus eget metus luctus
        accumsan id ultrices nunc. Sed at orci sed massa consectetur dignissim a
        sit amet dui. Duis commodo vitae velit et faucibus. Morbi vehicula
        lacinia malesuada. Nulla placerat augue vel ipsum ultrices, cursus
        iaculis dui sollicitudin. Vestibulum eu ipsum vel diam elementum tempor
        vel ut orci. Orci varius natoque penatibus et magnis dis parturient
        montes, nascetur ridiculus mus.
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} — <strong>{{ people.name }}</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
import { ref, onMounted } from "vue";
import "animate.css";

export default {
  setup() {
    const people = ref({ name: "CODMA", age: 25 });

    const vCardMotion = {
      initial: {
        opacity: 0,
        y: 100,
        duration: 20,
      },
      visible: {
        opacity: 1,
        y: 0,
      },
    };

    const icons = [
      {
        icon: "mdi-github",
        link: "",
      },
    ];

    const vCardStyle = {
      opacity: 1,
    };

    const vCardContents = [
      "VUE.JS",
      "VUE.JS",
      "VUE.JS",
      "VUE.JS",
      "VUE.JS",
      "VUE.JS",
      "VUE.JS",
    ];

    function toDown() {
      const currentScrollPosition =
        window.pageYOffset || document.documentElement.scrollTop;
      console.log(currentScrollPosition);
    }

    onMounted(() => {});

    return { people, vCardMotion, vCardStyle, icons, vCardContents, toDown };
  },
};
</script>

<style scoped>
.v-enter-active,
.v-leave-active {
  transition: opacity 1s;
}
/* opacity:0에서 1까지 페이드인&페이드아웃하기 */
.v-enter,
.v-leave-to {
  opacity: 0;
}
</style>
