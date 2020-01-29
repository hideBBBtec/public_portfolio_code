<template>
  <v-container>
    <h1><font color="white" style="font-size: 50px;">{{ msg }}</font></h1>
  </v-container>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: function () {
    setInterval(() => { this.time-- }, 1000)
    return {
      msg_list: ["BE A FULL STACK ENGINEER", "CLOUD ENGINEER", "FRONT-END ENGINEER", "SERVER-SIDE ENGINEER", "DATA SCIENTIST", "IT CONSULTANT"],
      msg: "BE A FULL STACK ENGINEER",
      time: 5,
      cnt: 0,
    }
  },
  methods: {
    changeComment: function() {
      if (this.cnt >= 5) {
        this.cnt = 0
      } else {
        this.cnt++
      }
      this.msg = this.msg_list[this.cnt];
    }
  },
  watch: {
    time: function(v) {
      if (v <= 0) {
        this.time = 5
        this.changeComment()
      }
    }
  }
};
</script>
