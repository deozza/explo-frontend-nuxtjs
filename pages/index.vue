<template>
    <NuxtLayout name="default">
        <div>
            <p>hello world</p>

            <button @click="decrement" >-1</button>
            <p>{{ counter }}</p>
            <button @click="increment" >+1</button>

            <ul>
                <li v-for="fruit in fruitList" >{{ fruit.name.toUpperCase() }} : {{ fruit.price }}€</li>
            </ul>

            <Paragraph :counter />

        </div>
    </NuxtLayout>

</template>

<script lang="ts">
    import { ref } from 'vue';

    export default {
        name: 'IndexPage',
        layout: 'default',
        setup() {
            const counter = ref(0);
            const fruitList: Array<object> = [
                {
                    'name': 'pomme',
                    'price': 10
                },
                {
                    'name': 'poire',
                    'price': 100
                },
                {
                    'name': 'clementine',
                    'price': 1
                },
            ];

            return {
                counter,
                fruitList
            };
        },
        methods: {
            increment() {
                this.counter++;
            },
            decrement() {
                this.counter--;
            }
        }
    }
</script>

<style>
    p {
        color: red
    }
</style>