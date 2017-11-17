<template>
    <div class = "message" id = "message">
        <div class = "grid-container">
            <div class="large-8 medium-8 columns large-offset-2 medium-offset-2">
                <input-message :msg="message" @messageChanged="message=$event">
                    <h4 slot="footer">Your About to Send</h4>
                    <h4 slot="title">Message to Admin</h4>
                </input-message>
            </div>
        </div>
    </div>
</template>
<script>
    import Input from './Input.vue'
    export default {
        data() {
            return {
                message: ''
            }
        },
        components:{
            'input-message': Input
        }
    }

</script>

<style type = "scss">

</style>