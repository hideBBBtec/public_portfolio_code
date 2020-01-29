<template>
  <div>
    <div class="home">
      <HelloWorld test="hello"/>
    </div>
    <div>
      <!-- <v-btn class="mx-2" fab dark small color="light-blue"  href="https://twitter.com/intent/follow?screen_name=********"> -->
        <!-- <v-icon dark>mdi-twitter</v-icon> -->
      <!-- </v-btn> -->
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  components: {
    HelloWorld
  },
};
</script>
