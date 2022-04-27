<template>
    <panel :todos="mytodos"></panel>
</template>

<script>
import panel from '@/components/panel.vue'

export default {
    components:{
        panel
    },
    date(){
        return{
            mytodos:[
                {
                    tag: 'срочно',
                    date: 'сегодня',
                    name: 'ДЗ',
                },
                {
                    tag: 'несрочно',
                    date: 'сегодня',
                    name: 'егэ',
                },
                {
                    tag: 'срочно',
                    date: 'завтра',
                    name: 'мшп',
                },
                {
                    tag: 'срочно',
                    date: 'завтра',
                    name: 'ГУУ пойти',
                },
                {
                    tag: 'несрочно',
                    date: '24 апреля',
                    name: 'ненаю',
                }
            ],
        }
    }

}
</script>

<style>

</style>
