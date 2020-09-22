<template>
   <div>
       {{time}}
       <button
        @click="stopTimer"
       >
           STOP
       </button>
   </div>
</template>

<script>
let timerId = null;

export default {
  name: 'Timer',
  props: {
    initialValue: {
        type: Number,
        default: 100,
    }
  },
  data () {
      return {
          time: this.initialValue,
      }
  },
  methods: {
      timerInterval(callback, interval) {
          timerId = setInterval(() => {
              callback();
          }, interval);
      },

      startTimer() {
          this.timerInterval(() => {
              if (this.time <= 0) {
                  clearInterval(timerId);
                  return;
              }
              this.time--;
          },1000)
      },

      stopTimer() {
          clearInterval(timerId);
      },
  },

  mounted() {
      this.startTimer();
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
