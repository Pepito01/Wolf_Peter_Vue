<template>
  <table>
      <tr>
          <th><h1>Name</h1></th>
          <th><h1>Year</h1></th>
          <th><h1>Publisher</h1></th>
          <th><h1>F2P?</h1></th>
      </tr>
        <Tablazat
        v-for="Tabla in Tablazat"
        :key="Tabla.name"
        :Tabla="Tabla"
        @Tabla-delete="Deleted"
        />
        <tr>
            <td><input type="text" v-model="name"></td>
            <td><input type="date" v-model="year"></td>
            <td><input type="text" v-model="publisher"></td>
            <td><input type="text" v-model="free"></td>
            <td><button @click="New">Felvétel</button></td>
        </tr>
  </table>
</template>

<script>
import Tablazat from './Tablazat.vue'
export default {
    props: ['Tablazat'],
    components: {Tablazat},
    methods: {
        

        New(){
            this.$emit('item-hozzaad', {
                new:{
                    name:this.name,
                    year:this.year,
                    publisher:this.publisher,
                    free:this.free

                }
            })
             this.name = null 
            this.year = null 
            this.publisher = null 
            this.free = null
        },
        Delete(e){
            this.$emit('Tabla-delete', e)
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