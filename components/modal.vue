<template>
    <div>
        <div class="modal" :class="{'is-active': isShown}">
            <div class="modal-background"></div>
            <div class="modal-card">
                <header class="modal-card-head">
                    <p class="modal-card-title">
                        <slot name="title">
                            {{title}}
                        </slot>
                    </p>
                    <button class="delete" aria-label="close" @click="hide()"></button>
                </header>
                <section class="modal-card-body">
                    <slot name="content">
                        {{content}}
                    </slot>
                    <slot name="buttonCont"></slot>
                </section>
                <footer class="modal-card-foot">
                    <slot name="footer">
                        <button class="button is-success" @click="saveChanges()">Save Changes</button>
                        <button class="button" @click="hide()">Cancel</button>
                    </slot>
                </footer>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props:{
        content:{
            type: String,
            default: ''
        },
        title:{
            type: String,
            default: 'Nani'
        },
        /*buttonsFooter:{
            type: Element,
            default: <a class="button is-primary">Primary</a>
        }*/
    },
    data(){
        return{
            isShown: false
        }
    },
    methods:{
        show(){
            this.isShown = true
        },
        hide(){
            this.isShown = false
        },
        togle(){
            this.isShown = !this.isShown
        },
        saveChanges(){
            // some saving code
            this.hide()
        }
    }
}
</script>

