<template>
  <div class="index">
    <v-carousel 
      cycle 
      show-arrows-on-hover 
      hide-delimiter-background 
      delimiter-icon="mdi-minus" 
      height="100vh"
    > 
      <v-carousel-item v-for="(slide) in slides" :key="slide" width="100%" >
        <v-sheet
          :color="slide"
          height="100%"
          tile
        ></v-sheet>
      </v-carousel-item>
    </v-carousel>
    <div class="buttons">
      <v-row>
        <v-col v-for="link in links" :key="link" cols="12">
          <v-btn
            color="white"
            plain
            :disabled=link.disabled
          >{{link.name}}</v-btn>
        </v-col>
      </v-row>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'top',
  data(){
    return {
      slides:[
        'primary',
        'secondary',
        'yellow darken-2',
        'red',
        'orange',
      ],
      links: [
        {name: 'Top', disabled: false}, 
        {name: 'About me', disabled: false}, 
        {name: 'Works', disabled: true}, 
        {name: 'Hobbies', disabled: true},
      ],
      is_bottom: true
    }
  }
}
</script>

<style scoped>
.buttons{
  position: absolute; 
  top: 1vh;
}
</style>