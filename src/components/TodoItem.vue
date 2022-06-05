<template>
    <div class="container">
        <h3>{{message.task.title}}</h3>        
        <form @submit.prevent='addEvent'> 
            <input v-model='newEvent'></input>
            <button>Add New Event</button>
        </form>
        <ul>
            <li v-for="event of message.task.events">                 
                <span> {{event}}</span>                                
            </li>                        
        </ul>
        <button @click="toHide">Save</button>
    </div>
</template>

<script>
    export default {
        name: 'TodoItem',
        data() {
            return {
                isVisible: true,                
                newEvent: ''
            }
        },
        emits: ['response'],        
        methods: {
            toHide() {
               this.isVisible = false
               this.$emit('response', this.isVisible)
               console.log('hide', this.isVisible)
            },            
            addEvent(){
                this.message.task.events.push(this.newEvent)
                this.newEvent = ''
            }
        },
        props: {
            message: Object            
        }

    }
    

</script>

<style scoped>
    .container{
        background: #ffa;
        border-radius: 8px;
        padding: 15px;
        width: 300px; 
        position:  absolute;
        left: 400px;
        top: 100px;
    }
    h3{
        margin-top: 10px;
        margin-bottom: 10px;
    }
    ul{
        font-size: 24px;        
        list-style: none;        
    }

</style>