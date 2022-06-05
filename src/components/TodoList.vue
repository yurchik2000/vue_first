<template>
    <div>
        <form @submit.prevent='addTask'> 
            <input v-model='newTask'></input>
            <button>Add New Task</button>
        </form>
        <ul>
            <li v-for="item of taskList" :key="item.id"> 
                <input type="checkbox" v-model="item.done">
                <span :class="{done: item.done}"> {{item.task.title}}</span>                
                <button @click="toShow(item)">Edit</button>              
                <button @click="removeItem(item)"> Delete </button>
            </li>                        
        </ul>        
        <TodoItem v-show="isVisible" @response="childMessageReceived" :message="editedTask"/>
        {{isVisible}}
    </div>
</template>

<script>
    import TodoItem from '@/components/TodoItem'

    let id = 0;
    export default {
        name: 'TodoList',
        data() {
            return {
                newTask: '',          
                isVisible: false,      
                editedTask: {},
                taskList: [
                    {id: id++, 
                     task: {
                        title: 'Item 1',
                        events: ['Event 1', 'Event 2']
                    },
                    done: false},
                    {id: id++, 
                     task: {
                        title: 'Item 2',
                        events: ['Event 3', 'Event 4']
                    },
                    done: false},
                    {id: id++, 
                     task: {
                        title: 'Item 3',
                        events: ['Event 5', 'Event 6']
                    },
                    done: false}
                ]
            }
        },
        components: {
            TodoItem
        },
        methods:{
            addTask () {
                this.taskList.push({id: id++, 
                        task: {
                            title: this.newTask,
                            events: []
                        },
                        done: false})
                
                this.newTask = ''
            },
            removeItem(item) {                
                this.taskList = this.taskList.filter(t => t!=item)
            },            
            toShow(item){
                this.isVisible = true                
                this.editedTask = item
            },
            childMessageReceived(isVisible) {
                console.log('message', isVisible)
            }
        },        
    }
</script>

<style scoped>
    ul{
        font-size: 24px;        
        list-style: none;
    }
    li{
        margin-bottom: 10px;
    }
    button{
        display: in-line block;
        margin-left: 10px;        
        cursor: pointer;
    }
    .done{
        text-decoration: line-through;
    }
</style>