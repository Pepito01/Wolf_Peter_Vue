
<template>
  <tr>
    <td>
          {{name}}
    </td>
    <td>
        {{year}}     
    </td>
    <td>
        {{publisher}}
    </td>
    <td>
        {{free}}
    </td>
    <td><button @click="Delete">Delete</button></td>

  </tr>
</template>

<script>
export default {
    props: ['Tabla'],
    data() {
        return {
            name: this.Tabla.name,
            year: this.Tabla.year,
            publisher: this.Tabla.publisher,
            free: this.Tabla.free,
        }
    },
methods: {
    
        Delete(){
            this.$emit('Tabla-delete')
        },

         

    }
}
</script>