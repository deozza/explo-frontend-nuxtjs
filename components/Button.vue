<template>
    <button>
        {{ contentOfButton }}
    </button>
</template>


<script lang="ts">
export default {
  name: 'ButtonComponent',
  props: [
    'contentOfButton'
  ]
}
</script>


<style scoped>
    button {
        background-color: red;
        padding: 10px 5px;
        margin: 5px;
    }
</style>