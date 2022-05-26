<template>
  <v-app>
    <v-main id="scroll-target">
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  setup() {},
};
</script>

<style>
::-webkit-scrollbar {
  width: 10px;
  background: #000;
}

::-webkit-scrollbar-thumb {
  background: #777;
  border-radius: 8px;
  margin-right: 5px;
}
</style>
