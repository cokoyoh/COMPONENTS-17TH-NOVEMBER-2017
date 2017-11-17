<template>
    <div class = "message" id = "message">
        <div class = "grid-container">
            <div class="large-8 medium-8 columns large-offset-2 medium-offset-2">
                <h2>Your Message</h2>
                <input-message :msg="message" @messageChanged="message=$event"></input-message>
            </div>
        </div>
    </div>
</template>
<script>
    import Input from './Input.vue'
    export default {
        data() {
            return {
                message: 'This is the message from main component'
            }
        },
        components:{
            'input-message': Input
        }
    }

</script>

<style type = "scss">

</style>