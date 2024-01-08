<template>
    <div>
        <p v-if="isEven === true" >Le chiffre est pair</p>
        <p v-else>Le chiffre est impair</p>
    </div>
</template>

<script lang="ts">
import { computed } from 'vue';
    export default {
        name: 'ParagraphComponent',
        props: {
            counter: {
                type: Number,
                required: true,
                default: 0
            }
        },
        setup(props) {
            const isEven = computed(() => props.counter % 2 === 0);

            return {
                isEven
            }
        },
    }
</script>

<style scoped>
    p {
        color: blue
    }
</style>