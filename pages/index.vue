<template>
    <div>
        <p>bonjour</p>
        <p>Compteur : {{ counter }}</p>
        <p>Double : {{ double }}</p>
        <button @click="increment">Cliquer pour incrémenter</button>
        <button @click="decrement">Cliquer pour décrémenter</button>
        <Button contentOfButton="Texte passé en props" ></Button>
    </div>
</template>

<script lang="ts">
import { computed, ref } from 'vue'

export default {
  name: 'IndexPage',
  setup() {
    const counter = ref(0);
    const double = computed(() => counter.value * 2);

    return {
        counter,
        double
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