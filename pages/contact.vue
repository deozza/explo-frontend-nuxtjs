<template>
    <NuxtLayout name="custom">

        <div>
            <p>La page de contact</p>

        </div>
    </NuxtLayout>

</template>

<script lang="ts">
    import { computed, ref } from 'vue';

    export default {
        name: 'IndexPage',
        setup() {
            const counter = ref(0);
            const isEven = computed(() => counter.value % 2 === 0);

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
                isEven,
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
p{
    color: red
}
</style>