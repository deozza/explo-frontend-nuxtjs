<template>
    <NuxtLayout name="custom">

        <div>
            <input v-model="newItem" type="text" placeholder="new todo item..">
            <button @click="addToList">Add</button>

            <br/>
            <div v-for="(item, index) in todoList">
                <span>{{ item }}</span>
                <button @click="removeFromList(index)">❌</button>
                <br/>
            </div>
        </div>
    </NuxtLayout>

</template>

<script lang="ts">
    import { ref } from 'vue';

    export default {
        name: 'TodoPage',
        setup() {
            let newItem = '';
	
            let todoList  = ref([
                'Write my first post',
                'Upload the post to the blog',
                'Publish the post at Facebook'
            ]);

            return {
                newItem,
                todoList
            };
        },
        methods: {
            addToList() {
                this.todoList = [...this.todoList, this.newItem];
            },
            removeFromList(index: number) {
                this.todoList.splice(index, 1)
            }
        }
    }
</script>

<style>
p{
    color: red
}
</style>