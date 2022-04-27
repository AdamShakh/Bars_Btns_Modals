<template>
    <progress 
        class="progress" 
        :class="type"
        :value="value" :max="max"
        :style="'width: ' + progressWidth + '; height: ' + progressHeight + ';'">
    </progress>
</template>

<script>
export default {
    props:{
        type:{
            type: String,
            default: 'is-primary',
        },
        value:{
            default: 24,
            required: true
        },
        max:{
            default: 100,
        },
        progressWidth:{
            type: String,
            default: '600px'
        },
        progressHeight:{
            type: String,
            default: '20px'
        }
    },
}
</script>
