<template>
    <div id="right">
        <form @submit="addTodo">
            <input type="text" v-model="title" name="title" style="min-width:30px;" class="input-element">
            <button type="submit" style=" margin:auto; display:block; width: 500px ;  padding: 2px;
        font: 12pt sans-serif;   font:bold;">Add</button>

        </form>
    </div>
</template>


<script>

//import uuid from 'vue-uuid'
export default {
    name: 'AddTodo',
    data(){
        return{
            title:'',
            id: 6
        }
    },
    methods:{
        addTodo(e){
            e.preventDefault();

            const newTodoObj={
                id:this.id++,
                title: this.title,
                completed: false
                
            }
            
            this.$emit('add-todo', newTodoObj);
            this.title=''
        }
    }


}
</script>

<style>

input[type="text"] {
             display: block;
             margin : 0 auto;
        }
#left {
    float:left;
    width:100px;
    height: 20px;
    background: #ff0000;

}
.input-element {
        border: 0;
        padding: 2px;
        background: #fff;
        font: 12pt sans-serif;
        width: 1000px;
      
        height: 30px;
      }

</style>