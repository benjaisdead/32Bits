<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <ul>
        <li v-for="dato in juegos">
        {{ dato.nombre }}
        </li>
    </ul>

          <div id="laTabla">
                  <table border="1">
                    <tr>
                      <th>Codigo</th>
                      <th>Stock</th>
                      <th>Nombre</th>
                      <th>Precio</th>
                    </tr>
                    <tr v-for="registro in juegos" v-bind:style="`color: ${registro.color}`">
                      <td>{{ registro.codigo}}</td>
                      <td>{{ registro.nombre}}</td>
                      <td>{{ registro.stock}}</td>
                      <td>{{ registro.precio}}</td>
                    </tr>
                  </table>
          </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'DatosJuegos',
  props: {
    msg: String
  },
  computed:{
    ...mapState(["juegos"]),
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

#laTabla{
  text-align:center;
}
</style>
