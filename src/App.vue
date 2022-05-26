<template>
  <v-app>
    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    //
  }),
};
</script>

<style>
::-webkit-scrollbar {
  width: 15px;
  background: #000;
}

::-webkit-scrollbar-thumb {
  background: #777;
  border-radius: 8px;
  margin-right: 5px;
}
</style>
