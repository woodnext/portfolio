<template>
  <v-app dark>
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
      title: "woodnext",
      tab: null,
      items: [
        'Top', 'Profile', 'Works',
      ],
    }
  }
}
</script>
