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
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      title: "Shun Kotsugi",
      items: [
        'Top', 'About me', 'Works', 'hobbies'
      ],
    }
  }
}
</script>
