<template>
  <v-app dark>
    <Nuxt />
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
