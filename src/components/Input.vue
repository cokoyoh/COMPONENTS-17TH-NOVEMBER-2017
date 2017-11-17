<template>
    <div class = "input" id = "input">
        <div class = "grid-container">
            <slot name="title"></slot>
                <textarea name = "message_here" id = "message_here" rows = "5"
                          :value = "msg" @input="getMessage"
                          placeholder = "Write complaint here.."></textarea>
            <slot name="footer"></slot>
            {{msg}}
        </div>
    </div>
</template>
<script>
    export default {
        props: ['msg'],
        data() {
            return{
                message: ''
            }
        },
        methods:{
            getMessage(event){
                this.message = event.target.value;
                this.$emit("messageChanged", this.message)
            }
        }
    }

</script>

<style type = "scss">

</style>