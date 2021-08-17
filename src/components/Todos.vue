<template>
    <div>
        <h3>Here's your Todos</h3>
        <ul>
            <li v-bind:key="todo.id" v-for="todo in todos">
        <Todo v-bind:todo="todo" v-on:delete-todo="$emit('delete-todo', todo.id)"/>
      </li>
        </ul>
        <h2>Add More work in list</h2>

    </div>
</template>

    <script>
    import Todo from './Todo.vue';
    
    export default{
        name:'Todos',
        components:{
            Todo
        },
        props:[
            "todos"
        ]

            
        
    }
    </script>
    
<style>

h3{
    
    text-align: center;
    background: rgb(173, 215, 250);
    padding: 1rem;
    font-size: 2rem;
    border-bottom: 1px solid white;
    
}
h2{
    
    text-align: center;
    padding: 1rem;
    font-size: 1.5rem;
    
}
li{
    
    list-style-type: none;
            background: rgb(251, 253, 250);
            margin: 2px;
            padding: 10px 20px;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            text-align: center;

            
}
#left{
    float: left;
    background: rgb(245, 243, 159);
    width: 100px;
    height:  20px;
}
#center {

    display: inline-block;
    margin:0 auto;
    width:100px;
    height: 20px;
    background: #00ff00;
}



</style>