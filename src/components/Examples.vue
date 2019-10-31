<template>
    <div>
        <div class="card">
            <img src="../assets/image-placeholder.jpg" alt="Avatar">
            <div class="container">
                <h4><b>Example Title</b></h4>
            </div>
        </div>
        <!-- <div v-bind:key="todo.id" v-for="todo in todos">
            <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
        </div> -->
    </div>
</template>

<script>
// import TodoItem from './TodoItem.vue';

export default {
    name: "Examples"
    // components: {
    //     TodoItem
    // },
    // props: ["todos"]
}
</script>

<style scoped>
    .card {
        /* Add shadows to create the "card" effect */
        box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
        transition: 0.3s;
        border-radius: 5px;
        display: inline-block;
        padding: 10px;
        background: white;
    }

    /* On mouse-over, add a deeper shadow */
    .card:hover {
        box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
    }

    /* Add some padding inside the card container */
    .container {
        padding: 2px 16px;
        text-align: center;
    }

    img {
        border-radius: 5px 5px 0 0;
    }
</style>