<template>
    <div>
        <div class="tabs" :class="type">
            <ul>
                <li :class="{'is-active': tab.$data.isShown}" 
                    v-for="(tab, i) in tabs" 
                    :key="i">
                    <a @click="select(tab)">{{tab.$props.name}}</a>
                </li>
            </ul>
        </div>
        <slot></slot>
    </div>
</template>

<script>
export default {
    data(){
        return{
            tabs: []
        }
    },
    methods:{
        select(tab){
            this.tabs.forEach(item => {
                item.$data.isShown = tab.$props.name === item.$props.name
                //item.selected = (item != tab) ? false : true
            })
        }
    },
    mounted(){
        console.log(this.$children)
        this.tabs = this.$children

        /*this.$children.forEach(child => {
            console.log('ttt', child.$props.name)
            
            this.tabs.push({
                name: child.$props.name,
                selected: child.$props.selected
            });
        })*/
    },
    props:{
        type:{
            type: String
        }
    }
}
</script>
