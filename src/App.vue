<template>
  <div id="app">
    

    <svg viewBox="0 0 300 150">
      <polygon class="polymorph" points="300,150 0,150 0,0 300,0 300,50 	"/>
    </svg>

    <button id="btn" @click="introAnime">Enter</button>

    <div id="reveal">
      <h1>Not a whole lot here yet</h1>
      <p>Its' a work in progress, check back later to see me grow!</p>
      <button id="btn2" @click="reverseAnime">Close</button>
    </div>

  </div>
</template>

<script>
import Main from './components/Main.vue'

export default {
  name: 'app',
  components: {
    Main
  },
  methods: {
    introAnime() {
      this.$anime({
      targets: '.polymorph',
      points: [
        { value: '73,33 0,150 0,0 300,0 300,50 ' },
        { value: '67,27 0,130 0,0 280,0 280,0' }
      ],
      easing: 'easeOutQuad',
      duration: 1000,
      loop: false
      });
      this.$anime({
        targets: '#reveal',
        opacity: 1,
        duration: 1000,
        translateY: 200,
      })
    },
    reverseAnime() {
      this.$anime({
      targets: '.polymorph',
      points: [
        { value: '300,150 0,150 0,0 300,0 300,50' }
      ],
      easing: 'easeOutQuad',
      duration: 800,
      loop: false
      });
      this.$anime({
        targets: '#reveal',
        opacity: 0,
        duration: 500,
        translateY: -800,
      })
    }
  }
}
</script>

<style>
.polymorph {
  fill: #900000;
}
#reveal {
  position: absolute;
  color:#900000;
  right: 25%;
  top:0;
  opacity: 0;
  width: 30%;
  transform: translateY(-800px);
}

#btn, #btn2{
  position:absolute;
  margin: 10em auto auto;
  left: 0;
  right: 0;
  width: 30%;
  background: none;
  border: 1px solid #fff;
  border-radius: 5px;
  padding: 15px;
  color: #fff;
  font-size: 1.5em;
  cursor: pointer;
  outline:0;
}

#btn2 {
  width: auto;
  margin: 30px auto;
  background: #900000;
}

p{
  font-size: 1.2em;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
  margin: 0px;
}

</style>
