<template>
    <div>
        <div class="container">
            <TodoList />
        </div>
    </div>

</template>

<script>
    import TodoList from '@/components/TodoList'

    export default {
        name: 'TodoMain',
        components: {
            TodoList
        }
    }
</script>

<style scoped>
    .container{
        padding: 10px;
        max-width: 1200px;
        margin: 0 auto;
        background: #f9f9f9;
        text-align: left;        
    }

</style>