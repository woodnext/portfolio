<template>
  <v-app dark>
    <v-app-bar
      fixed
      app
      dark
      color="black"
      elevation="0"
    >
      <v-app-bar-title v-text="title"/>
      <v-spacer/>
      <v-btn
        v-for="item in items"
        :key="item"
        plain
        color="white"
      >
        {{item}}
      </v-btn>
    </v-app-bar>
    <v-main>
      <Nuxt />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      title: "WoodNext ",
      items: [
        'Top', 'About me', 'Works', 'hobbies'
      ],
    }
  }
}
</script>
