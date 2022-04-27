<template>
<div id='mainDiv'>
    <div id='menu'>
        <nav class="panel">
            <p class="panel-heading">
                TODOS
            </p>

            <p class="panel-tabs">
                <a v-for="(dateL, i) in dates"
                   :key="i" >
             
                </a>
            </p>
            <a
             class="panel-block is-active">
                <span class="panel-icon">
                <svg class="svg-inline--fa fa-book fa-w-14" aria-hidden="true" data-prefix="fas" data-icon="book" 
                role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" data-fa-i2svg="">
                    <path fill="currentColor" 
                    d="M448 360V24c0-13.3-10.7-24-24-24H96C43 0 0 43 0 96v320c0 53 43 96 96 96h328c13.3 0 24-10.7 24-24v-16c0-7.5-3.5-14.3-8.9-18.7-4.2-15.4-4.2-59.3 0-74.7 5.4-4.3 8.9-11.1 8.9-18.6zM128 134c0-3.3 2.7-6 6-6h212c3.3 0 6 2.7 6 6v20c0 3.3-2.7 6-6 6H134c-3.3 0-6-2.7-6-6v-20zm0 64c0-3.3 2.7-6 6-6h212c3.3 0 6 2.7 6 6v20c0 3.3-2.7 6-6 6H134c-3.3 0-6-2.7-6-6v-20zm253.4 250H96c-17.7 0-32-14.3-32-32 0-17.6 14.4-32 32-32h285.4c-1.9 17.1-1.9 46.9 0 64z">
                    </path>
                </svg><!-- <i class="fas fa-book" aria-hidden="true"></i> -->
                </span>
                
            </a>
        </nav>
    </div>
    <!--  --------  -->
    <div id='todosList'>
        <nav>
            <p class="panel-heading">
                TODOS list
            </p>

            <a  v-for="(todo, i) in todos"
                :key="i"
                class="panel-block" :class="{'is-active': todoList(todo.date, todo.tag)}">
               {{todo.name}}
            </a>
        </nav>
    </div>
</div>


</template>

<script>
export default {
    props:{
        todos:{
            type: Array,
            required: true
        },
        dateTo:{
            default: 'сегодня'
        },
        tagTo:{
            default: 'срочно'
        }
    },
    methods:{
        todoList(date, tag){
            return (date == this.dateTo && tag == this.tagTo) ? true : false
        }
    },
    computed:{
        dates(){
            let arr = []
            console.log(this.todos)
            
            return arr
        },
        tag(){

        },
        todoList(){
            
        }
    }
}
</script>

<style>
    #main{
        display: flex;
        justify-content: center;
    }
    #menu{
        width: 40%;
    }
    #todosList{
        width: 10%;
    }
</style>
