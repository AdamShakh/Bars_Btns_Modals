<template>
    <a 
        @click="click()"
        class="button"
        :class="{'is-loading': loading, 'is-static': iSstatic,
        'is-warning': warning, 'is-primary': primary, 'is-danger': danger, 
        'is-success': success, 'is-link': link, 'is-info': info}"
        :disabled="disable">
        <slot name="content">{{text}}</slot>
    </a>
</template>




<script>

export default {
    props:{
        text:{
            type: String,
            default: 'Click'
        },
        click:{
            required: false // @click="click()"
            //@click=("$emit('click')")
        },
        disable:{
            type: Boolean,
            default: false
        },
        loading:{
            type: Boolean,
            default: false
        },
        iSstatic:{
            type: Boolean,
            default: false
        },
        warning:{
            type: Boolean,
            default: false
        },
        primary:{
            type: Boolean,
            default: false
        },
        danger:{
            type: Boolean,
            default: false
        },
        success:{
            type: Boolean,
            default: false
        },
        link:{
            type: Boolean,
            default: false
        },
        info:{
            type: Boolean,
            default: false
        },
    }
}
</script>


