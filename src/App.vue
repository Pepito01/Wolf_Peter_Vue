<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Kedvenc videó-játékok listája</h1>
    <jatek :Tablazat="Tablazat" @item-hozzaad="Created" @Tabla-torles="Deleted"/>
  </div>
</template>


<script>
import jatek from './components/Jatek.vue'
export default {
  name: 'App',
  components: {
    jatek
  },
  data() {
    return {
      Tablazat: [
        {
          name: 'Counter-Strike: Global Offensive',
          year: '2012.08.21.',
          publisher: 'Valve',
          free: 'Nem'
        },
        {
          name: 'Call of Duty: Vanguard',
          year: '2021.10.10.',
          publisher: 'Digital Extremes',
          free: 'Nem'
        },
        {
          name: 'Enlisted',
          year: '2021.04.2.',
          publisher: 'Gaijin Entertainment',
          free: 'Igen'
        },
      ]
    }
  },
  methods: {
    Created(e){
        this.Tablazat.push({nev: e.nev, ev: e.ev, publisher: e.publisher, free: e.free})
    },
    Deleted(e){
      this.Tablazat.splice(this.Tablazat.indexOf(e.original), 1);
      }
    }
  }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
