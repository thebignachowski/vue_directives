<template>
  <div>
    <h1>Directivas</h1>
    <hr>
    <!--<span v-text="title"></span>-->
    <span>{{title}}</span>
    <div v-html="html">

    </div>
    <h4>Tu edad es: {{age}}</h4>
    <h2 v-show="age >= 18">Mayor de edad</h2>
    <h2 v-show="age < 18">Menor de edad</h2>
    <button @click="add()">ADD</button>
    <button @click="dis()">DIS</button>
    <ul>
      <li v-for="usuario, index in usuarios" :key="index">{{usuario}} - {{ index }}</li>
    </ul>
    <ul>
      <li v-for="(value, name) in persons" :key="name">
        {{value}} - {{name}}
      </li>
    </ul>
    <div>
      <img v-bind:src="url" v-bind:alt="alt" />
    </div>
    <div @click="click" class="contador">
      Clicks: {{clicks}}
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    title: "Hola desde Vue3!",
    html: "<h3>Soy un h3</h3>",
    age: 17,
    usuarios: ["Juan", "Nacho", "Nachowski", "Juanchowski"],
    persons: [
      {
        name: "Nachowski",
      },
      {
        name: 'Carmen',
      },
      {
        name: 'José',
      }
    ],
    clicks: 0,
    url: 'https://es.vuejs.org/images/logo.png',
    alt: 'Imagen vue'
  }),
  methods: {
    add(){
      this.age++
    },
    dis() {
      this.age--
    },
    click() {
      this.clicks++ 
    }
  }
}
</script>


<style scoped>
div {
  text-align: center;
  margin: 0 1rem;
}
button {
  margin: 0 1rem;
}
ul {
  list-style: none;
}
.contador {
  background-color: tomato;
  color: snow;
  font-weight: bold;
  height: 30rem;
  margin: 2rem 0;
}
</style>