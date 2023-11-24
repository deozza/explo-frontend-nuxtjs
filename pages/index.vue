<template>
    <div>
        <p>bonjour</p>
        <p>Compteur : {{ counter }}</p>
        <p>Double : {{ double }}</p>
        <button @click="increment">Cliquer pour incrémenter</button>
        <button @click="decrement">Cliquer pour décrémenter</button>
        <Button contentOfButton="Texte passé en props" ></Button>

      <p v-if="isEven" >Le nombre est pair</p>
      <p v-else>Le nombre est impair</p>

      <ul>
        <li v-for="fruit in fruitList">{{ fruit.name }} : {{ fruit.price }}€</li>
      </ul>
    </div>
</template>

<script lang="ts">
import { computed, ref } from 'vue'

export default {
  name: 'IndexPage',
  setup() {
    const counter = ref(0);
    const double = computed(() => counter.value * 2);
    let isEven = computed(() => counter.value % 2 === 0)
    let fruitList: Array<object> = [
      {
        'name': 'ananas',
        'price': 10
      },
      {
        'name': 'pomme',
        'price': 20
      },
      {
        'name': 'poire',
        'price': 3
      },
      {
        'name': 'orange',
        'price': 90
      }
    ]; 

    return {
        counter,
        double,
        isEven,
        fruitList
    }
  },
  methods:{
    increment(){
      this.counter++
    },
    decrement(){
      this.counter--
    }
  }
}
</script>

<style>
    button {
        background-color: greenyellow;
        padding: 10px 5px;
        margin: 5px;
    }
</style>