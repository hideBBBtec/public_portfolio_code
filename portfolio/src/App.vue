<template>
  <v-app>
    <v-img src="@/static/img4.jpg" :height="height" :width="width">
      <Header />
      <v-content>
        <v-container fluid fill-height>
          <v-layout justify-left align-left>
              <router-view></router-view>
          </v-layout>
        </v-container>
      </v-content>
    </v-img>
  </v-app>
</template>

<script>
import Header from './components/Header';

export default {
  name: 'App',

  components: {
    Header,
  },
  data: function () {
    return {
      width: window.innerWidth,
      height: window.innerHeight
    }
  },
  methods: {
    handleResize: function() {
      // resizeのたびにこいつが発火するので、ここでやりたいことをやる
      this.width = window.innerWidth;
      this.height = window.innerHeight;
    }
  },
  mounted: function () {
    window.addEventListener('resize', this.handleResize)
  },
  beforeDestroy: function () {
    window.removeEventListener('resize', this.handleResize)
  }
};
</script>
