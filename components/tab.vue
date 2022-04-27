<template>
   <div v-show="isShown">
       <slot></slot>
   </div>
</template>

<script>
export default {
    props:{
        name:{
            required: true,
        },
        selected:{
            type: Boolean,
            default: false
        },
        wid:{
            default: 100
        }
    },
    data(){
        return{
            isShown: this.selected
        } 
    }
}
</script>
